<script setup>
import Tasks from '../components/Tasks.vue'
import AddTask from '../components/AddTask.vue'

defineProps({
    addTaskVisible: Boolean
})
</script>

<script>
export default {
    data: () => ({
        tasks: []
    }),
    methods: {
        addTask(task) {
            fetch("http://localhost:5000/tasks", {
                method: "POST",
                body: JSON.stringify(task),
                headers: {
                    "Content-Type": "application/json"
                }
            })
                .then(res => res.json())
                .then((task) => {
                    this.tasks = [...this.tasks, task]
                })
        },
        deleteTask(id) {
            if (confirm('Are you sure?')) {
                fetch(`http://localhost:5000/tasks/${id}`,
                    {
                        method: "DELETE",
                    })
                    .then(() => {
                        this.tasks = this.tasks.filter(task => task.id !== id)
                    })
            }
        },
        toggleReminder({ id, reminder }) {
            fetch(`http://localhost:5000/tasks/${id}`,
                {
                    method: "PATCH",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify({
                        reminder: !reminder
                    })
                })
                .then(res => res.json())
                .then(res => {
                    this.tasks = this.tasks.map((task) => task.id === id ? {
                        ...task,
                        ...res
                    } : task)
                })
        }
    },
    async created() {
        const res = await fetch("http://localhost:5000/tasks");
        const tasks = await res.json();
        this.tasks = tasks;
    }
}
</script>

<template>
    <AddTask v-show="addTaskVisible" @on-submit="addTask" />
    <Tasks :tasks="tasks" @delete-task="deleteTask" @toggle-reminder="toggleReminder" />
</template>