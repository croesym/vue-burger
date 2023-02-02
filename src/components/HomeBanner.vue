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
  background-position: center;
  height: 500px;
  display: flex;
  align-items: center;
  min-height: 300px;
}

#main-banner h1 {
  color: #fff;
  font-size: 60px;
  background-color: rgba(34, 34, 34, 0.6);
  padding: 20px 40px;
  max-width: 80%;
}

@media (max-width: 767px) {
  #main-banner h1 {
    font-size: 30px;
    padding: 10px 20px;
  }
}
</style>
