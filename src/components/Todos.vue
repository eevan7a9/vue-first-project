<template>
  <div>
    <ul v-bind:key="todo.id" v-for="todo in todos">
      <li>{{todo.title}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Todos",
  props: ["todos"]
};
</script>
<style scoped>
</style>
