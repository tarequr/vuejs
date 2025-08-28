<script setup>
import Hero from "@/components/Hero.vue";
import HomeCards from "@/components/HomeCards.vue";
import JobListngs from "@/components/JobListngs.vue";
</script>

<template>
  <Hero />
  <HomeCards />
  <JobListngs :limit="3" />
</template>
