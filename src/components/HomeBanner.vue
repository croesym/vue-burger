<template>
  <div id="main-banner">
    <h1>Make Your Burger</h1>
  </div>
</template>

<script>
export default {
  name: "HomeBanner",
};
</script>

<style scoped>
#main-banner {
  background-image: url("../img/burger.jpg");
  background-size: cover;
  background-position: 0 -450px;
  height: 500px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

#main-banner h1 {
  color: #fff;
  font-size: 60px;
  background-color: #222;
  padding: 20px 40px;
}
</style>
