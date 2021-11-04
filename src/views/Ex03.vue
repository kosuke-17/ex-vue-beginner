<template>
  <div>
    <input type="text" v-model="first" />
    +
    <input type="text" v-model="second" />
    ={{ addNum }}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class sampleComponent extends Vue {
  private first = '';
  private second = '';
  private addCalc = 0;

  get addNum(): number {
    this.addCalc = parseInt(this.first) + parseInt(this.second);
    return this.addCalc ? this.addCalc : 0;
  }
}
</script>

<style scoped>
.ex1 {
  width: 300px;
  border: 1px solid black;
}
</style>
