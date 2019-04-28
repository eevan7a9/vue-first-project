<template>
  <div id="app">
    <HeaderLayout></HeaderLayout>
    <router-view/>
  </div>
</template>
<script>
import HeaderLayout from "./components/layout/Header"
export default {
  name:'app',
  components:{
    HeaderLayout
  }
}
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
