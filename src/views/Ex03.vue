<template>
  <div>
    <input type="text" v- />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class sampleComponent extends Vue {
  private name = '';
  private age = 0;
  private ageTenLater = 0;
  private hobbies: string[] = [];
  private url = '#';
  private imageUrl = '';
  private noCanClick = false;

  onClick(): void {
    this.name = '田村孝輔';
    this.age = 25;
    this.ageTenLater = this.age + 10;
    this.hobbies[0] = 'スイム';
    this.hobbies[1] = 'バイク';
    this.hobbies[2] = 'ラン';
    this.url = 'https://www.rakus-partners.co.jp/';
    this.imageUrl = 'img/irobot.jpg';
    this.noCanClick = true;
  }
}
</script>

<style scoped>
.ex1 {
  width: 300px;
  border: 1px solid black;
}
</style>
