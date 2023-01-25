<template>
  <div>
    <footer id="vueFooter">
      <p>Make Your Burger &copy; 2022</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "vueFooter",
};
</script>

<style scoped>
#vueFooter {
  height: 200px;
  background-color: #222;
  border-top: 4px solid #111;
  color: #fcba03;
  display: flex;
  align-items: center;
  justify-content: center;
  bottom: 0;
  width: 100%;
}
</style>
