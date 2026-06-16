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
        Awesome! :heart:<br /><br />
        {{ selectedPlace }} it is! :tada:
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DateOptions",

  data() {
    return {
      selectedPlace: "",
    };
  },

  methods: {
    selectPlace(place) {
      this.selectedPlace = place;
    },
  },
};
</script>

<style src="./Home.css"></style>