<template>
    <li>
        <input type="text" v-if="editing" v-bind:value="todo.title" @input="todo.title = $event.target.value" v-on:keyup.enter="editing = !editing">
        <p v-bind:class="todo.completed ? 'completed': ''" v-else-if="!editing" @click="todo.completed = !todo.completed">{{ todo.title }}</p>
        <button @click="editing = !editing" >Edit</button>
        <button @click="$emit('delete-todo', todo.id)">Remove</button>
    </li>
</template>

<script>
export default {
    name: 'Todo',
    props: [
        'todo'
    ],
    data: () => ({
        editing: false
    }),
}
</script>

<style scoped>
    li {
        padding: 15px;
        background: white;
        margin-bottom: 10px;
        color: black;
        display: flex;
        align-items: center;
    }

    p {
        flex: 1;
    }

    .completed {
        text-decoration: line-through
    }

    button {
        padding: 10px;
        border: none;
        background: #31475E;
        color: white;
        margin-left: 15px;
        outline: none;
    }

    input[type="text"] {
        flex: 1;
        border: 1px solid lightgrey;
        background: white;
        padding: 9px;
        outline: none;
    }

</style>