<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <Formulario @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <!-- pra cada tarefa no nosso array de tarefas queremos fazer alguma coisa -->
        <!-- o key vai identificar o index da lista, pra vue saber quando ele vai ou nao renderizar -->
        <Tarefa
          v-for="(tarefa, index) in tarefas"
          :key="index"
          :tarefa="tarefa"
        />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BarraLateral from "./components/BarraLateral.vue";
import Formulario from "./components/Formulario.vue";
import Tarefa from "./components/Tarefa.vue";
import type ITarefa from "./interfaces/ITarefa";

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    Formulario,
    Tarefa,
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
    };
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    },
  },
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
