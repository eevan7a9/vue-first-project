<template>
  <div id="app">
    <HeaderLayout></HeaderLayout>
    <AddTodo v-on:add-todo="addItem"></AddTodo>
    <Todos v-bind:todos="todos" v-on:delete-todoItem="delItem"></Todos>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import HeaderLayout from "./components/layout/Header";
import AddTodo from "./components/AddTodo";
import axios from "axios";

export default {
  name: "app",
  components: {
    Todos,
    HeaderLayout,
    AddTodo
  },
  data() {
    return {
      todos:[],
      // todos: [
      //   {
      //     id: 1,
      //     title: "Learn Vuejs",
      //     completed: true
      //   },
      //   {
      //     id: 2,
      //     title: "Learn Django",
      //     completed: false
      //   },
      //   {
      //     id: 3,
      //     title: "Learn Wordpress Theme Development",
      //     completed: false
      //   }
      // ],
    };
  },
  methods: {
    delItem(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then((res) => this.todos = this.todos.filter(todo => todo.id !== id))
      .catch();
      // console.log(id)
    },
    addItem(newItem) {
      const {title, completed} = newItem;
      axios.post('https://jsonplaceholder.typicode.com/todos?_limit=5', {
        title:title,
        completed:completed
      })
      .then((res) => this.todos = [...this.todos, res.data])
      .catch();
    },
  },
  created(){ /** created() will run right away */
      axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then((res) => this.todos = res.data)
      .catch();
    }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
