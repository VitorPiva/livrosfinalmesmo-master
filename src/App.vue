<script setup>
import HeaderComp from "@/components/template/HeaderComp.vue";
import FooterComp from "@/components/template/FooterComp.vue";
</script>
<template>
  <HeaderComp />
  <main>
    <RouterView />
  </main>
  <FooterComp />
</template>

<style>
@import "@/assets/base.css";
@import "@/assets/style.css";

#app {
  max-width: 1280px;
  margin: 0 auto;
  font-weight: normal;
  /* padding: 2rem; */
  height: 100vh;

  font-weight: normal;
}

a {
  color: rgb(255, 255, 255);
  text-decoration: none;
}

header,
footer {
background: rgb(0, 128, 53);
  color: rgb(255, 255, 255);
  height: 15%;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  padding-left: 2rem;
}

main {
  height: 70%;
}
</style>
