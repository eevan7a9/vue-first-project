<template>
  <div id="app">
    <h4>{{msg}}</h4>
    <Todos v-bind:todos="todos"></Todos>
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
          title: "first",
          completed: false
        },
        {
          id: 2,
          title: "second",
          completed: false
        },
        {
          id: 3,
          title: "third",
          completed: false
        }
      ],
      msg: "Hello World"
    };
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
