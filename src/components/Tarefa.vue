<template>
  <Box>
    <div class="columns">
      <div class="column is-7">
        <!-- se a descrição nao existe, vai ter a legenda a seguir -->
        {{ tarefa.descricao || "Tarefa sem descrição" }}
      </div>
      <div class="column">
        <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </Box>
</template>
<script lang="ts">
import type ITarefa from "@/interfaces/ITarefa";
import { defineComponent, type PropType } from "vue";
import Cronometro from "./Cronometro.vue";
import Box from "./Box.vue";

export default defineComponent({
  name: "Tarefa",
  components: {
    Cronometro,
    Box,
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
