<script setup>
defineEmits(["on-submit"])
</script>

<script>
export default {
    data() {
        return {
            title: "",
            time: "",
            reminder: false,
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault();

            if (!this.title) {
                alert('Please enter task');
                return;
            }

            this.$emit("on-submit", {
                title: this.title,
                time: this.time,
                reminder: this.reminder,
            })

            this.title = ""
            this.time = ""
            this.reminder = false
        }
    }
}
</script>

<template>
    <form class="wrapper">
        <div class="form-control">
            <label for="task">Task</label>
            <input id="task" type="text" placeholder="Enter task..." v-model="title" />
        </div>
        <div class="form-control">
            <label for="time">Date & Time</label>
            <input id="time" type="text" placeholder="Enter data and time..." v-model="time" />
        </div>
        <div>
            <label for="reminder">Reminder</label>
            <input id="reminder" type="checkbox" v-model="reminder" style="margin-left: 4px;" />
        </div>
        <button type="submit" @click="onSubmit">Save Task</button>
    </form>
</template>

<style scoped>
.wrapper {
    padding: 5px;
    border-bottom: 1px solid rgb(208, 208, 208);
    margin-bottom: 10px;
    padding-bottom: 10px;
}

.form-control {
    display: flex;
    justify-content: space-between;
    margin-block: 2px;
}

button {
    width: 100%;
    background-color: hsla(160, 100%, 37%, 1);
    color: black;
    text-transform: uppercase;
    font-weight: bold;
    border: 0;
    letter-spacing: 0.2rem;
    padding-block: 10px;
    margin: 0;
    margin-top: 5px;
}
</style>