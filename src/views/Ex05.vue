<template>
  <div class="main">
    <!-- 数字入力 -->
    <div>
      名前：<br />
      <input type="text" v-model="name" />
    </div>
    <div>
      年齢：<br />
      <input type="text" v-model.number="age" />
    </div>
    <div>
      コメント：<br />
      <textarea cols="30" rows="5" v-model="comment" />
    </div>
    <hr />
    <div>入力値：</div>
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}</div>
    <pre>コメント：<br>{{ comment }}</pre>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class sampleComponent extends Vue {
  private name = '';
  private age = '';
  private comment = '';
}
</script>

<style scoped>
.main {
  width: 300px;
}
</style>
