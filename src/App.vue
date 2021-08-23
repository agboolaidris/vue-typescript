<template>
  <Joblist :jobs="jobs" />
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Joblist from "./components/Job.vue";
import Job from "./types/Jobs";

export default defineComponent({
  name: "App",
  components: {
    Joblist,
  },
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
