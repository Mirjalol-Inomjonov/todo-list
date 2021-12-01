<template>
  <form @submit.prevent="onSubmit" class="add-form">
    <div class="form-control">
      <label for="text">Task</label>
      <input
        v-model="text"
        type="text"
        name="text"
        id="text"
        placeholder="Enter your a task"
      />
    </div>
    <div class="form-control">
      <label for="day">Day and Time</label>
      <input
        v-model="day"
        type="text"
        name="day"
        id="day"
        placeholder="Enter day and time"
      />
    </div>
    <div class="form-control form-control-check">
      <input v-model="reminder" type="checkbox" value="reminder" id="check" />
      <label for="check">Select</label>
    </div>
    <button class="btn btn-block">Save Task</button>
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit() {
      if (!this.text) {
        alert("Please! enter your a task");
      }

      const newTask = {
        id: Math.floor(Math.random() * 10000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this$emit('add-task', newTask)



      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.add-form {
  margin-bottom: 40px;
  .form-control {
    margin: 20px 0;
    label {
      display: block;
    }
    input {
      width: 100%;
      height: 40px;
      margin: 5px;
      padding: 3px 7px;
      font-size: 17px;
    }
  }
  .form-control-check {
    display: flex;
    align-items: center;
    label {
      display: inline-block;
    }
    input {
      display: inline-block;
      width: 20px;
      height: 20px;
    }
  }
}
</style>
