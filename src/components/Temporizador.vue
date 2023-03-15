<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <Cronometro :tempoEmSegundos="tempoEmSegundos" />
    <button class="button" @click="iniciar" :disabled="cronometroRodando">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="finalizar" :disabled="!cronometroRodando">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Cronometro from "./Cronometro.vue";
export default defineComponent({
  name: "Temporizador",
  //emits: emite um ou mais eventos
  emits: ["aoTemporizadorFinalizado"],
  components: {
    Cronometro,
  },
  //definindo um estado inicial pro componente
  data() {
    return {
      //variaveis
      tempoEmSegundos: 0,
      cronometro: 0,
      cronometroRodando: false,
    };
  },
  //funções que ele é capaz de executar
  methods: {
    iniciar() {
      //para desabilitar o botao
      this.cronometroRodando = true;
      //salva o setInterval numa variavel pra poder limpar depois e parar de cronometrar
      //a cada 1000 segundos ele vai executar o setInterval
      this.cronometro = setInterval(() => {
        this.tempoEmSegundos += 1;
      }, 1000);
    },
    finalizar() {
      //para desabilitar o botao
      this.cronometroRodando = false;
      //parando o cronometro
      clearInterval(this.cronometro);
      //metodo que recebe 2 params: nome do evento que ta emitindo, payload(carga de dados que vai junto)
      //zerando cronometro ao clicar em stop
      this.$emit("aoTemporizadorFinalizado", this.tempoEmSegundos);
      this.tempoEmSegundos = 0;
    },
  },
});
</script>
<style></style>
