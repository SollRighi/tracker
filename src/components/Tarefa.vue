<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">{{ tarefa.descricao }}</div>
      <div class="column">
        <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import type ITarefa from "@/interfaces/ITarefa";
import { defineComponent, type PropType } from "vue";
import Cronometro from "./Cronometro.vue";

export default defineComponent({
  name: "Tarefa",
  components: {
    Cronometro,
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true,
    },
  },
});
</script>

<!-- scoped significa que esse style só vai ser aplicado pra ele ou pros filhos dele -->
<style scoped>
.box {
  background: #faf0ca;
}
</style>
