<template>
    <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">       <!-- is-complete css styling class will be rendered conditionally -->
        <p>
            <input type="checkbox" v-on:change="markComplete(todo)">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(todo) { 
            todo.completed = !todo.completed;
        }                    
    }
} 
</script> <!-- for the markComplete function we can acces the data through this.todo -->

<style scoped>
     .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
    }
    .is-complete {
        text-decoration: line-through;
    }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
    }
</style>