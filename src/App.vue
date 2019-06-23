<template>
    <div id="app">
        <Header v-bind:todos="todos.length"/>
        <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
        <AddTodo  v-on:add-todo="addTodo"/>
    </div>
</template>

<script>
import Header from './components/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

import uuid from 'uuid';

export default {
    name: 'app',
    components: {
       Todos,
       Header,
       AddTodo
    },
    data: () => ({
        todos: []
    }),
    methods: {
        deleteTodo(id) {
            this.todos = this.todos.filter(todo => todo.id !== id);
        },
        addTodo(todo) {
            this.todos.unshift({
                id: uuid.v4(),
                title: todo,
                completed: false,
            });
        },
    },
};
</script>

<style>
    * {
        padding: 0;
        margin: 0;
        font-family: sans-serif;
        box-sizing: border-box;
        -webkit-appearance: none;
    }

    body {
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        align-content: center;
    }

    #app {
        width: 50%;
        height: 50%;
        display: flex;
        flex-direction: column;
    }

    @media (max-width: 768px) {
        body {
            background: red;
        }
        #app {
            width: 100%;
            height: 100%;
        }
    }
</style>