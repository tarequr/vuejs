<script setup>
import jobData from "@/jobs.json";
import JobListng from "./JobListng.vue";
import { ref, defineProps } from "vue";

defineProps({
  limit: Number,
});

const jobs = ref(jobData.jobs);
</script>

<template>
  <section class="bg-green-50 px-4 py-10">
    <div class="container-xl lg:container m-auto">
      <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
        Browse Jobs
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <JobListng
          v-for="job in jobs.slice(0, limit || jobs.length)"
          :key="job.id"
          :job="job"
        />
      </div>
    </div>
  </section>
</template>
