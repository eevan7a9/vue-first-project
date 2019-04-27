<template>
  <div>
    <ul v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todoItem=todo v-on:delete-todoItem="$emit('delete-todoItem', todo.id)"></TodoItem>
    </ul>
    <h1>{{greete}}</h1>
  </div>
</template>
<script>
import TodoItem from './TodoItem';

export default {
  name: "Todos",
  props: ["todos",],
   components: {
    TodoItem
  },
  data(){ 
    return {
      greete: "hellow Worlds",
    }
  }
};
</script>
<style scoped>
</style>
