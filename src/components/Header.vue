<template>
    <header>
        <h1>Todos ({{todos}})</h1>
    </header>
</template>

<script>
export default {
    name: "Header",
    props: [
        "todos"
    ]
}
</script>

<style scoped>
    header {
        padding: 15px;
        background: #3FB984;
        color: white;
        display: flex;
        align-items: center;
    }

    h1 {
        flex: 1;
    }
</style>
