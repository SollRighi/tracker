<template>
  <header>
    <h1>
      <img src="../assets/oneHome.png" alt="" />
    </h1>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "BarraLateral",
});
</script>

<style scoped>
header {
  background-color: black;
  width: 100%;
  height: 100vh;
  padding: 1rem;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
