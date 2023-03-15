<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulario para criação de uma nova tarefa"
      >
        <!-- v-model serve pra lincar o estado do meu componente com a descricao da input -->
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="descricao"
        />
      </div>
      <div class="column">
        <!-- @significa ouvir um evento -->
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from "./Temporizador.vue";
export default defineComponent({
  name: "Formulario",
  components: {
    Temporizador,
  },
  //metodo que retorna o estado pra gente (ele retorna um objeto)
  data() {
    return {
      descricao: "",
    };
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      this.$emit("aoSalvarTarefa", {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao,
      });
      this.descricao = "";
    },
  },
});
</script>
