 <template>
     <div style="width:100; padding: 10px 0 10px 0;">
       <form @submit="addTodo">
             <input class="textInput" v-model="title" type="text" name="title" id="title" placeholder="title...">
             <input class="btnSubmit" type="submit" value="Submit">
       </form>
     </div>
 </template>

 <script>
//  import uuid from "uuid";
 export default {
     name: "AddTodo",
     data(){
         return{
             title :"",
         }
     },
     methods : {
         addTodo(event){
            event.preventDefault();
            const createdTodo = {
                // id:uuid.v4(), not needed when we use jsonplaceHolder
                title: this.title,
                completed: false,
            }
            this.$emit('add-todo', createdTodo);             
         }

     }
 }
 </script>
 
 <style scoped>
 .textInput{
     width: 78%;
     background: ghostwhite;
     color:#333;
     line-height: 40px;
     margin-left: 1%;
 }
 .btnSubmit{
     width: 20%;
     background: green;
     line-height: 40px;
     margin-right: 1%;
 }
 </style>
 
 