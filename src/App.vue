<script setup>
import { ref } from "vue";

const name = ref("Tarequr Rahman Sabbir");
const status = ref(true);
const tasks = ref(["Task 1", "Task 2", "Task 3", "Task 4", "Task 5"]);
const link = ref("https://www.google.com");

const newTask = ref("");

const addTask = () => {
  if (newTask.value.trim() === "") {
    alert("Please enter a task.");
    return;
  }

  tasks.value.push(newTask.value);
  newTask.value = "";
};

const deleteTask = (index) => {
  tasks.value.splice(index, 1);
};

const toggleStatus = () => {
  status.value = !status.value;
};
</script>

<template>
  <div>
    <h1>{{ name }}</h1>
    <p v-if="status">Status: Active</p>
    <p v-else>Status: Inactive</p>

    <form @submit.prevent="addTask">
      <label for="newTask">New Task: </label>
      <input
        type="text"
        id="newTask"
        name="newTask"
        v-model="newTask"
        placeholder="Add a new task"
      />
      <button type="submit">Add Task</button>
    </form>

    <h3>Tasks</h3>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <span>{{ task }}</span>
        <button @click="deleteTask(index)">x</button>
      </li>
    </ul>

    <a :href="link" target="_blank">Go to Google</a>

    <p v-if="tasks.length > 0">You have {{ tasks.length }} tasks.</p>
    <p v-else>You have no tasks.</p>

    <!-- <button v-on:click="status = !status">Change Status</button> -->
    <button v-on:click="toggleStatus">Change Status</button>
  </div>
</template>
