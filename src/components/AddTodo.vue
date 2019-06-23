<template>
    <div>
        <input type="text" v-bind:value="todo" placeholder="Ex. Do my homework." @input="todo=$event.target.value;" v-on:keyup.enter="addTodo()">
        <button @click="addTodo()">Add todo</button>
    </div>
</template>

<script>
export default {
    name: 'AddTodo',
    data: () => ({
        todo: ""
    }),
    methods: {
        addTodo(){
            if(this.todo !== ""){
                this.$emit('add-todo', this.todo);    
                this.todo = "";
            };
        },
    },
};
</script>

<style scoped>
    div {
        padding: 15px;
        background: #3FB984;
        display: flex;
    }

    input {
        flex: 1;
        padding: 15px;
        border: none;
        margin-right: 15px;
        outline: none;
    }

    button {
        padding: 15px;
        border: none;
        background: #31475E;
        color: white;
        outline: none;
    }
</style>
