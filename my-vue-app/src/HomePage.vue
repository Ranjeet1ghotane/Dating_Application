<template>
  <div class="container">
    <div class="date-card">
      <div class="heart">❤️</div>

      <h1>Will You Go On A Date With Me 😶‍🌫️</h1>

      <p class="subtitle">
        I promise good food, great conversations, and lots of smiles 😊
      </p>

      <div class="button-container" ref="buttonContainer">
        <button class="yes-btn" @click="sayYes">
          Yes 💖
        </button>

        <button
          ref="noBtn"
          class="no-btn"
          :style="{
            left: noButtonPosition.left + 'px',
            top: noButtonPosition.top + 'px'
          }"
          @mouseover="moveNoButton"
        >
          No 😅
        </button>
      </div>

      <div v-if="message" class="message">
        {{ message }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",

  data() {
    return {
      message: "",
      noButtonPosition: {
        left: 380,
        top: 50,
      },
    };
  },

  methods: {
    sayYes() {
         this.$emit("accepted");
    },

    moveNoButton() {
      const container = this.$refs.buttonContainer;
      const btn = this.$refs.noBtn;

      const containerWidth = container.clientWidth;
      const containerHeight = container.clientHeight;

      const buttonWidth = btn.offsetWidth;
      const buttonHeight = btn.offsetHeight;

      const maxX = containerWidth - buttonWidth;
      const maxY = containerHeight - buttonHeight;

      this.noButtonPosition = {
        left: Math.floor(Math.random() * maxX),
        top: Math.floor(Math.random() * maxY),
      };
    },
  },
};
</script>

