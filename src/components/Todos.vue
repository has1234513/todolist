<template>
    <div>
        <div  v-for="todo in todos" v-bind:key="todo.id"  >
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>                           <!-- todo is reference to line above (not todos)-->
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
    name: "Todos",
     components: {
        TodoItem
    },
    props: ["todos"]
}
</script>

<style scoped>
    
</style>