<template>
    <div class="container">
        <div class="card">
            <div class="heart">❤️</div>

            <h1>When Should We Meet?</h1>
            <p>Select a date and time for our special moment 😊</p>

            <div class="selected-place">
                📍 {{ place }}
            </div>

            <div class="input-group">
                <label>📅 Select Date</label>
                <input type="date" v-model="selectedDate" :min="today" @change="validateTime" />
            </div>

            <div class="input-group">
                <label>⏰ Select Time</label>
                <input type="time" v-model="selectedTime" :min="minTime" />
            </div>

            <button class="confirm-btn" :disabled="!selectedDate || !selectedTime" @click="confirmDate">
                Confirm Date ❤️
            </button>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from "vue";

const props = defineProps({
    place: {
        type: String,
        default: "",
    },
});

const selectedDate = ref("");
const selectedTime = ref("");

const today = new Date().toISOString().split("T")[0];

const minTime = computed(() => {
    if (selectedDate.value === today) {
        const now = new Date();

        const hours = String(now.getHours()).padStart(2, "0");
        const minutes = String(now.getMinutes()).padStart(2, "0");

        return `${hours}:${minutes}`;
    }

    return "00:00";
});

const validateTime = () => {
    selectedTime.value = "";
};

const emit = defineEmits(["date-confirmed"]);

const confirmDate = () => {
  emit("date-confirmed", {
    date: selectedDate.value,
    time: selectedTime.value,
  });
};
</script>

<style src="../styles/DateTime.css"></style>