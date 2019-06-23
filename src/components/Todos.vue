<template>
    <ul>
        <Todo v-for="todo in todos" v-bind:key="todo.id" v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
    </ul>
</template>

<script>
import Todo from './Todo';

export default {
    name: "Todos",
    props: [
        'todos'
    ],
    components: {
        Todo
    },
    methods: {
        deleteTodo: (id) => {
            console.log("Hola")
            this.todos.filter(x => x.id !== id)
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        padding: 15px;
        background: #31475E;
        flex: 1;
        overflow-y: scroll;
    }
</style>
