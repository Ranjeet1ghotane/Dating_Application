<script setup>
import { ref } from "vue";
import HomePage from "./HomePage.vue";
import DateOptions from "./DateOptions.vue";

const showDateOptions = ref(false);

const handleAccepted = () => {
  showDateOptions.value = true;
};
</script>

<template>
  <HomePage
    v-if="!showDateOptions"
    @accepted="handleAccepted"
  />

  <DateOptions
    v-else
  />
</template>