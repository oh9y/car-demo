<script setup lang="ts">
import HelloWord from "./components/HelloWord.vue";
import Car from "./components/Car.vue";
</script>

<template>
  <header>

    <Car></Car>
  </header>
</template>

<style scoped>
header {
  line-height: 1.5;
}

/* eslint-disable-next-line prettier/prettier */
.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
