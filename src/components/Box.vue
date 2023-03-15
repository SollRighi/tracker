<template>
  <!-- outra forma de definir o estilo usando :style e data  -->
  <div class="box has-text-weight-bold" :style="estilos">
    <!-- o que tiver dentro do componente Tarefa, vai ser renderizado aqui no slot -->
    <slot></slot>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Box",
  data() {
    return {
      //dessa forma pode facilitar quando quisermos modificar o estilo conforme o estado, tipo vermelho pra erro etc
      estilos: {
        // "background-color": "#faf0ca",
        // backgroundColor: "#faf0ca",
        background: "#faf0ca",
      },
    };
  },
});
</script>

<!-- <style scoped>
.box {
  background: #faf0ca;
}
</style> -->
