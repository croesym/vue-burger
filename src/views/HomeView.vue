<template>
  <HomeBanner />
  <div class="main-container">
    <h1>Monte o seu Burger</h1>
    <BurgerForm />
  </div>
</template>

<script>
import BurgerForm from "../components/BurgerForm.vue";
import HomeBanner from "../components/HomeBanner.vue";
export default {
  name: "HomeView",
  components: {
    HomeBanner,
    BurgerForm,
  },
};
</script>
