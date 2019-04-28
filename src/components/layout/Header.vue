<template>
    <div class="e7_bg">
        <h3>{{header}}</h3>
    <div id="nav">
      <router-link class="nav_item" to="/">Home</router-link> |
      <router-link class="nav_item" to="/about">About</router-link>
    </div>
    </div>
</template>
 
 <script>
 export default {
     name:'HeaderLayout',
     data(){
         return{
             header: "Todo App",
         }
     }
 }
 </script>
 
 <style scoped>
    .e7_bg{
        background: rgb(73, 11, 75);
        text-align: center;
        padding: 20px ;
        color: antiquewhite;
    }
    .nav_item{
        color: ghostwhite;
        text-decoration: none;
    }
 </style>
 