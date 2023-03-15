<template>
  <section>
    <strong> {{ tempoDecorrido }} </strong>
  </section>
</template>
<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "Cronometro",
  //tudo que recebe do componente pai (formulario)
  props: {
    tempoEmSegundos: {
      type: Number,
      default: 0,
    },
  },
  //propriedade computada: monitora uma informação e conforme ela muda, ele reage e se atualiza
  computed: {
    tempoDecorrido(): string {
      //00:00:00
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>
<style></style>
