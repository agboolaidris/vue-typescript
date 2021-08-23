<template>
  <ul v-for="job in jobs" :key="job.id">
    <li>{{ job.title }}</li>
  </ul>
</template>

<script lang="ts">
import Job from "../types/Jobs";
import { defineComponent, PropType } from "vue";

export default defineComponent({
  name: "JobList",
  props: {
    jobs: {
      type: Array as PropType<Job[]>,
      required: true,
    },
  },
  setup() {
    return {
      name: "",
    };
  },
});
</script>

<style scoped></style>
