<template>
  <ul v-for="job in order_jobs" :key="job.id">
    <li>
      <h2>{{ job.title }} {{ job.location }}</h2>
      <p>{{ job.salary }}Naira</p>
    </li>
  </ul>
</template>

<script lang="ts">
import { defineComponent, PropType, computed } from "vue";
import Job from "../types/Jobs";
import OrderTerm from "../types/OrderTerm";

export default defineComponent({
  name: "JobList",
  props: {
    jobs: {
      type: Array as PropType<Job[]>,
      required: true,
    },
    order: {
      type: String as PropType<OrderTerm>,
      required: true,
    },
  },
  setup(props) {
    const order_jobs = computed(() => {
      return [...props.jobs].sort((a: Job, b: Job) => {
        return a[props.order] > b[props.order] ? 1 : -1;
      });
    });
    return {
      order_jobs,
    };
  },
});
</script>

<style scoped></style>
