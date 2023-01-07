<script setup>
import Task from "./Task.vue";

defineProps({
    tasks: Array
})
defineEmits(["delete-task", "toggle-reminder"])
</script>

<script>
export default {
    methods: {
        deleteTask(id) {
            this.$emit('delete-task', id)
        },
        toggleReminder(task) {
            this.$emit('toggle-reminder', task)
        },
    }
}
</script>

<template>
    <div v-for="task in tasks">
        <Task :task="task" @delete-task="deleteTask" @toggle-reminder="toggleReminder" />
    </div>
</template>