<template>
  <div>
    <div class="ex1">
      <div>名前：{{ name }}</div>
      <div>年齢：{{ age }}</div>
      <div>１０年後の年齢：{{ ageTenLater }}</div>
      <div>
        趣味：<span v-for="(hobby, i) of hobbies" :key="i">{{ hobby }} </span>
      </div>
      <br />
      <a :href="url">自社ページリンク</a>
      <br />
      <br />
      <br />
      <img :src="imageUrl" alt="好きな画像" />
      <br />
    </div>
    <button type="button" v-on:click="onClick" :disabled="noCanClick">
      ボタン
    </button>
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
