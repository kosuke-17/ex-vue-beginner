<template>
  <div class="main">
    <!-- 数字入力 -->
    <input type="text" v-model.number="first" />
    <br />
    <input type="text" v-model.number="second" />
    <br />
    <input type="text" v-model.number="third" />
    <br />
    <!-- 入力合計表示 -->
    <div>税抜き価格：{{ priceCalc }}円</div>
    <div>税込み価格：{{ priceInTaxCalc }}円</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class sampleComponent extends Vue {
  private first = 0;
  private second = 0;
  private third = 0;
  private price = 0;
  private priceStr = '';
  private priceAndcTax = 0;
  private priceAndTaxStr = '';

  // 税抜き価格表示(カンマあり)
  get priceCalc(): string {
    this.price = this.first + this.second + this.third;
    this.priceStr = this.price.toLocaleString();
    return this.priceStr;
  }
  // 税込み価格表示(カンマあり)
  get priceInTaxCalc(): string {
    this.priceAndcTax = this.first + this.second + this.third;
    this.priceAndTaxStr = this.priceAndcTax.toLocaleString();
    return this.priceAndTaxStr;
  }
}
</script>

<style scoped>
.main {
  width: 250px;
  border: 1px solid black;
  text-align: center;
  padding: 10px 0;
}
</style>
