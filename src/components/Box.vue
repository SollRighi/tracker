<template>
  <div class="box has-text-weight-bold">
    <!-- o que tiver dentro do componente Tarefa, vai ser renderizado aqui no slot -->
    <slot></slot>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Box",
});
</script>

<style scoped>
.box {
  background: #faf0ca;
}
</style>
