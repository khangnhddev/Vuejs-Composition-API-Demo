<template>
  <div>
    <h1>Counter: {{ count }}</h1>
    <p>Doubled: {{ doubledCount }}</p>
    <button @click="increase">Increase</button>
    <button @click="decrease">Decrease</button>
    <button @click="reset">Reset</button>
  </div>
</template>

<script>
import { ref, computed, onMounted } from "vue";

export default {
  name: "Counter",

  setup() {
    // Reactive state
    const count = ref(0);

    // Computed property to calculate the doubled count
    const doubledCount = computed(() => count.value * 2);

    // Methods to mutate the count
    const increase = () => {
      count.value++;
    };

    const decrease = () => {
      count.value--;
    };

    const reset = () => {
      count.value = 0;
    };

    // Lifecycle hook: Runs once the component is mounted
    onMounted(() => {
      console.log("Counter component is mounted! Khang test ok ok");
    });

    // Expose to template
    return {
      count,
      doubledCount,
      increase,
      decrease,
      reset,
    };
  },
};
</script>

<style>
/* Add some styles if needed */
button {
  margin-right: 10px;
}
</style>
