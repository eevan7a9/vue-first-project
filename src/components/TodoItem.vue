<template>
    <div class="todo-item" v-bind:class="{'is-complete':todoItem.completed}">
        <p>
            <input type="checkbox" name="" id="todoCheckBox" v-on:change="isComplete()">
            {{todoItem.title}}
            <button class="del" @click="$emit('delete-todoItem', todoItem.id)">
                x
            </button>
        </p>
            
    </div>
</template>
<script>
export default {
    name: "TodoItem",
    props:[
        "todoItem",
    ], 
    methods:{
        isComplete(){
            this.todoItem.completed = !this.todoItem.completed;
        },
    }
}
</script>
<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #cccccc dotted;
    }
    .is-complete {
        text-decoration: line-through;
    }
    .del{
        background: grey;
        color: red;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>


