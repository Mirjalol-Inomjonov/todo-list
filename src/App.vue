<template>
  <div id="app">
    <div class="container">
      <Header title="Track" />
      <AddTask @add-task="addTask" />
      <Tasks
        @toggle-reminder="toggleReminder"
        @remove-task="removeTask"
        :tasks="tasks"
      />
    </div>
    <router-view />
  </div>
</template>

<script>
import AddTask from "./components/AddTask.vue";
import Header from "./components/Header";
import Tasks from "./components/Tasks";

export default {
  components: {
    Header,
    Tasks,
    AddTask,
  },

  data() {
    return {
      title: "Track",
      tasks: [],
    };
  },
  methods: {
    removeTask(id) {
      if (confirm("Are you delete this task?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },

    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },

    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Leverpool was created",
        day: "march 1st 1989 at 2:30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Barcelona was created",
        day: "january 1st 1549 at 5:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Real Madrid was created",
        day: "december 1st 1879 at 1:30pm",
        reminder: true,
      },
    ];
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap");
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: "Poppins", sans-serif;
  user-select: none;
}
#app {
  padding: 35px;
  min-height: 100vh;
  background: #eee;
}
.container {
  max-width: 500px;
  min-height: 300px;
  margin: 0 auto;
  overflow: auto;
  padding: 30px;
  border: 1px solid steelblue;
  border-radius: 5px;
  background: #fff;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
  &:focus {
    outline: none;
  }
  &:active {
    transform: scale(0.98);
  }
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
