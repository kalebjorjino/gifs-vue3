<template>
  <main>
    <NavBar />
    <div class="container mx-auto">
      <RouterView />
    </div>
    <Footer />
  </main>
</template>

<script>

import { RouterView } from "vue-router";
import NavBar from "./components/NavBar.vue";
import Footer from "./components/Footer.vue";

export default {
  components: { RouterView, NavBar, Footer },
};
</script>

<style scoped>
main {
   border-radius: 13px;
   box-shadow: 3px 3px 7px #ccc;
   padding: 2rem;
}
</style>

