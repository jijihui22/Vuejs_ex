<script setup>
const rawHtml = '<a href="">link</a>';
const pid = 10;
const isButtonDisabled = true;
const objectOfAttrs = {
      id: 'container',
      class: 'wrapper'
    }
const number = 20;
const ok = false;
const message = '안녕하세요';
const id = 30;
const sayHello = (msg)=>{alert(msg);};
const url = "https://www.naver.com";
const attributeName = 'href';
const items = [
  { id:0, title:'html'},
  { id:1, title:'css'},
  { id:2, title:'javascript'}
];
const onSubmit = ()=>{
  alert('제출되었습니다.')
}
</script>
<template>
  <div class="layout">
    <h1>This is an template page</h1>
    <br>
    <h2>html 출력</h2>
    <p>{{ rawHtml }}</p>
    <p><span v-html="rawHtml"></span></p>
    <hr>
    <h2>속성 바인딩</h2>
    <div v-bind:id="pid"></div>
    <div :id="pid"></div>
    <hr>
    <h2>불리언 바인딩</h2>
    <button :disabled="isButtonDisabled">버튼</button>
    <button :disabled="!isButtonDisabled">버튼</button>
    <hr>
    <h2>여러속성 바인딩</h2>
    <div v-bind="objectOfAttrs"></div>
    <hr>
    <h2>자바스크립트 표현식</h2>
    {{ number + 1 }}
    {{ ok ? '예' : '아니오' }}
    {{ message.split('').reverse().join('') }}
    <div :id="`list-${id}`"></div>
    <hr>
    <h2>함수 호출</h2>
    <!-- <span :title="sayHello('hello')"></span> -->
    <div>{{ sayHello('hello') }}</div>
    <hr>
    <h2>디렉티브</h2>
    <a v-bind:href="url">네이버</a>
    <a :href="url">네이버</a>
    <hr>
    <h2>동적인 인자</h2>
    <a v-bind:[attributeName]="url"> ... </a>
    <hr>
    <h2>v-for 반복문</h2>
    <div v-for="item in items" :key="item.id">
      {{ item.title }}
    </div>
    <hr>
    <h2>on 이벤트</h2>
    <div>
      <button type="button" v-on:click="sayHello('안녕')">안녕</button>
      <button type="button" @click="sayHello('안녕')">안녕</button>
      <button type="button" @mouseover="sayHello('안녕')">안녕</button>
    </div>
    <hr>
    <h2>수식어</h2>
    <form action="" @submit.prevent="onSubmit">
      <button>제출</button>
    </form>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .layout {
    min-height: 100vh;
    /* display: flex;
    align-items: center; */
  }
}
</style>
