<template>
  <button @click="order_logic('title')">title</button>
  <button @click="order_logic('location')">location</button>
  <button @click="order_logic('salary')">salary</button>
  <Joblist :jobs="jobs" :order="order_value" />
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Joblist from "./components/Job.vue";
import Job from "./types/Jobs";
import OrderTerm from "./types/OrderTerm";

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
    const jobs = ref<Job[]>([
      {
        title: "Software Developer",
        salary: 2000,
        location: "Lagos",
        id: 1,
      },
      {
        title: "Physicist",
        salary: 400,
        location: "Ibadan",
        id: 2,
      },
    ]);
    const order_value = ref<OrderTerm>("title");

    const order_logic = (order: OrderTerm) => {
      order_value.value = order;
    };

    return {
      ...toRefs(state),
      jobs,
      order_logic,
      order_value,
    };
  },
});
</script>

<style></style>
