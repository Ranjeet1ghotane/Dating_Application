<template>
  <div class="container">
    <div class="card">

      <div class="success">🎉</div>

      <h1>It's A Date!</h1>

      <p class="subtitle">
        Everything is set for our special day ❤️
      </p>

      <div class="details">

        <div class="item">
          <span>📍 Destination</span>
          <strong>{{ place }}</strong>
        </div>

        <div class="item">
          <span>📅 Date</span>
          <strong>{{ date }}</strong>
        </div>

        <div class="item">
          <span>⏰ Time</span>
          <strong>{{ time }}</strong>
        </div>

      </div>

      <div class="message">
        I can't wait to see you 😊💕
      </div>

      <div class="hearts">
        ❤️ 💖 💕 💘 💝
      </div>

    </div>
  </div>
</template>

<script setup>
defineProps({
  place: String,
  date: String,
  time: String,
});
</script>

<style src="./DateConfirm.css"></style>