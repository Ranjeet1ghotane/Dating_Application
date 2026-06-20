<template>
  <div class="container">
    <div class="date-card">
      <div class="heart">❤️</div>

      <h1>Where Would You Like To Go?</h1>

      <p class="subtitle">
        Choose your dream date destination 😊
      </p>

      <div class="date-options">
        <button
          class="option-btn"
          @click="selectPlace('🕯️ Candlelight Dinner')"
        >
          🕯️ Candlelight Dinner
        </button>

        <button
          class="option-btn"
          @click="selectPlace('🌊 Lakeside Dinner')"
        >
          🌊 Lakeside Dinner
        </button>

        <button
          class="option-btn"
          @click="selectPlace(' 🌆 Rooftop Dinner')"
        >
          🌆 Rooftop Dinner
        </button>
      </div>

      <div v-if="selectedPlace" class="message">
        Awesome! ❤️<br /><br />
        {{ selectedPlace }} it is! 😊
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DateOptions",

  methods: {
    selectPlace(place) {
      this.$emit("place-selected", place);
    },
  },
};
</script>

<style src="../styles/DateOptions.css"></style>