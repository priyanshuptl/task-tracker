<script>
export default {
    methods: {
        addTask() {
            console.log('Clicked!');
        }
    },
    emits: ["toggle-add-task"],
    props: ["addTaskVisible"]
}
</script>

<template>
    <header>
        <h1>Task Tracker</h1>
        <button @click="$emit('toggle-add-task')">{{ addTaskVisible? 'Remove': 'Add Task' }}</button>
    </header>
</template>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
}
</style>