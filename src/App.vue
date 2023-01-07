<script setup>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
import AddTask from './components/AddTask.vue'
</script>

<script>
export default {
  data: () => ({
    num: 0,
    name: "Priyanshu Patel",
    image: "data:image/jpeg;base64,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",
    loading: false,
    addTaskVisible: false,
    tasks: []
  }),
  methods: {
    generateRandomNumber() {
      this.num = Math.round(Math.random() * 100)
    },
    async generateRandomUser() {
      this.loading = true;
      const res = await fetch('https://randomuser.me/api');
      console.log(await res.json());
      this.loading = false;
    },
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
    },
    toggleAddTask() {
      this.addTaskVisible = !this.addTaskVisible;
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
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <h1>Custom Message</h1>
      <h1 class="green">{{ name }}</h1>
      <img :src="image" :alt="name">
      <button v-on:click="generateRandomNumber" class="green">Random Number Generator</button>
      <button v-on:click="generateRandomUser" class="green" :disabled="loading">{{
        loading? "Loading...": "Random User Generator"
      }}</button>
      <label>Number: {{ num }}</label>
    </div>
  </header>

  <main>
    <!-- <TheWelcome /> -->
    <Header :addTaskVisible="addTaskVisible" @toggle-add-task="toggleAddTask" />
    <AddTask v-if="addTaskVisible" @on-submit="addTask" />
    <Tasks :tasks="tasks" @delete-task="deleteTask" @toggle-reminder="toggleReminder" />
  </main>
</template>

<style>
button {
  padding-inline: 20px;
  padding-block: 5px;
  background-color: transparent;
  border: 2px solid hsla(160, 100%, 37%, 1);
  border-radius: 5px;
  cursor: pointer;
  margin: 5px;
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}
</style>

<style scoped>
header {
  line-height: 1.5;
}

main {
  border-radius: 5px;
  border: 1px solid rgb(208, 208, 208);
  padding: 10px;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

img {
  width: 80px;
  height: 80px;
  margin: 15px;
}

label {
  margin-left: 10px;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    /* padding-right: calc(var(--section-gap) / 2); */
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
