<template>
  <div id="app">
    <ContadorDefault :valorInicial="10" /> <!-- ':' passa o valor como number -->
    <ContadorClasse :valorInicial="100" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import ContadorDefault from '@/components/ContadorDefault.vue';
import ContadorClasse from '@/components/ContadorClasse.vue';

@Options({
  components: {
    ContadorDefault, ContadorClasse
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
