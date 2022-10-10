<template>
  <div>
    <h1>Contador (Classe)</h1>
    <h2>{{ Valor }}</h2>
    <h3>{{ getParOuImpar() }}</h3>
    <h3>{{ ParOuImpar }}</h3>
    <button @click="setValor(-1)">Dec</button>
    <button @click="setValor(1)">Inc</button>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop } from 'vue-property-decorator';

@Options({
  props: {
    valorInicial: Number
  },
  watch: {
    valorInicial(val: number) {
      this.valor = val
    }
  }
})
export default class ContadorClasse extends Vue {
  
  // decorator para passar o tipo de valor que esperamos receber como propriedade
  @Prop(Number) public readonly valorInicial?: number
  private valor = this.valorInicial || 0

  public setValor(delta: number) {
    this.valor += delta
  }

  public get Valor(): number {
    return this.valor
  }

  public getParOuImpar(): string {
    return this.valor % 2 === 0 ? 'Par' : 'Ímpar'
  }

  public get ParOuImpar(): string {
    return this.valor % 2 === 0 ? 'Par' : 'Ímpar'
  }
}
</script>

<style>

</style>
