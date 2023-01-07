<script setup>
defineProps({
    task: Object
})
defineEmits(["delete-task", "toggle-reminder"])
</script>

<template>
    <div :class="[task.reminder ? ' reminder' : '', 'task']" @dblclick="$emit('toggle-reminder', task)">
        <span class="title-span">
            <h3>{{ task.title }}</h3>
            <b @click="$emit('delete-task', task.id)">x</b>
        </span>
        <p>{{ task.time }}</p>
    </div>
</template>

<style>
.task {
    background-color: rgba(51, 51, 51, 0.4);
    padding: 5px;
    padding-inline: 10px;
    margin-block: 5px;
}

.task.reminder {
    border-left: 3px solid rgb(87, 151, 87);
}

.title-span {
    display: flex;
    justify-content: space-between;
    /* align-items: center; */
}

.title-span b {
    font-weight: 500;
    cursor: pointer;
}
</style>