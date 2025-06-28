<script setup lang="ts">
// import HelloWorld from './components/HelloWorld.vue'
import Content from './components/Content.vue'
import Question from './components/Question.vue';
import Form from "./components/Form.vue";
import VHtml from './components/VHtml.vue';  
import SearchInput from './components/SearchInput.vue';

function onAdd(value: number) {
  console.log('子組件傳來的值:', value)
}
const a= '安安';
</script>

<template>
  <!-- <div>
    <a href="https://vite.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div> -->
  <!-- <HelloWorld msg="Vite + Vue" /> -->
  <!-- <Content /> -->
  <!-- <Question /> -->
  <!-- <Form/> -->
  <VHtml title="標題" content="<p>hi~~</p>" @add="onAdd"/>
  <SearchInput v-model="a"></SearchInput>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
