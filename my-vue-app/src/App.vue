<script setup>
import { ref } from "vue";
import HomePage from "././components/HomePage.vue";
import DateOptions from "././components/DateOptions.vue";
import DateTime from "././components/DateTime.vue";
import DateConfirmationPage from "././components/DateConfirmationPage.vue";

const currentPage = ref("home");

const selectedPlace = ref("");
const selectedDate = ref("");
const selectedTime = ref("");

const handleAccepted = () => {
  currentPage.value = "options";
};

const handlePlaceSelected = (place) => {
  selectedPlace.value = place;
  currentPage.value = "datetime";
};

const handleDateConfirmed = (data) => {
  selectedDate.value = data.date;
  selectedTime.value = data.time;

  currentPage.value = "confirmation";
};
</script>

<template>
  <HomePage v-if="currentPage === 'home'" @accepted="handleAccepted" />

  <DateOptions v-else-if="currentPage === 'options'" @place-selected="handlePlaceSelected" />

  <DateTime v-else-if="currentPage === 'datetime'" :place="selectedPlace" @date-confirmed="handleDateConfirmed" />

  <DateConfirmationPage v-else-if="currentPage === 'confirmation'" :place="selectedPlace" :date="selectedDate"
    :time="selectedTime" />
</template>