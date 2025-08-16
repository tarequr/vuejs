<script>
export default {
  name: "App",
  data() {
    return {
      name: "Tarequr Rahman Sabbir",
      status: true,
      tasks: ["Task 1", "Task 2", "Task 3", "Task 4", "Task 5"],
      link: "https://google.com",
    };
  },

  methods: {
    toggleStatus() {
      // this.status = !this.status;
      if (this.status) {
        this.status = false;
      } else {
        this.status = true;
      }
      // this.status = this.status ? false : true;
      // this.status = this.status === true ? false : true;
      // this.status = !this.status;
    },
  },
};
</script>

<template>
  <div>
    <h1>{{ name }}</h1>
    <p v-if="status">Status: Active</p>
    <p v-else>Status: Inactive</p>

    <h3>Tasks</h3>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">{{ task }}</li>
    </ul>

    <a :href="link" target="_blank">Go to Google</a>

    <p v-if="tasks.length > 0">You have {{ tasks.length }} tasks.</p>
    <p v-else>You have no tasks.</p>

    <!-- <button v-on:click="status = !status">Change Status</button> -->
    <button v-on:click="toggleStatus">Change Status</button>
  </div>
</template>
