<template>
  <div class="message-container">
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  name: "OrderMessage",
  props: { message: String },
};
</script>

<style scoped>
.message-container {
  color: #004085;
  background-color: #cce5ff;
  border-color: #b8daff;
  border: 2px solid #88daff;
  border-radius: 5px;
  padding: 10px;
  max-width: 400px;
  margin: 30px auto;
}
</style>
