<template>
  <h1>{{ jobs[0].location }}</h1>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "./types/Jobs";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    const state = reactive({
      name: "Idris",
      age: 20 as number,
    });
    const jobs = ref<[Job]>([
      {
        title: "Software Developer",
        salary: 2000,
        location: "Lagos",
        id: 2,
      },
    ]);
    return {
      ...toRefs(state),
      jobs,
    };
  },
});
</script>

<style></style>
