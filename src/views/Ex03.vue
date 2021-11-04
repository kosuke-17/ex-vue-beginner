<template>
  <div>
    <input type="text" v-model="first" />
    +
    <input type="text" v-model="second" />
    ={{ addCalc }}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class sampleComponent extends Vue {
  private first = '';
  private second = '';
  private addNum = 0;

  get addCalc(): number {
    this.addNum = parseInt(this.first) + parseInt(this.second);
    return this.addNum ? this.addNum : 0;
  }
}
</script>

<style scoped>
.ex1 {
  width: 300px;
  border: 1px solid black;
}
</style>
