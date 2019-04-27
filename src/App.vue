<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:delete-todoItem="delItem"></Todos>
  </div>
</template>

<script>
import Todos from "./components/Todos";
export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Learn Vuejs",
          completed: true
        },
        {
          id: 2,
          title: "Learn Django",
          completed: false
        },
        {
          id: 3,
          title: "Learn Wordpress Theme Development",
          completed: false
        }
      ],
      msg: "Hello World"
    };
  },
  methods: {
    delItem(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
      // console.log(id)
    }
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
