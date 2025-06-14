<script setup lang="ts">
import { computed, ref, watch } from 'vue'

let showAnswer = ref(false);
const label = computed(() => {
   return  showAnswer.value ? '隱藏答案' : '顯示答案'
})

const toggleAnswer = () => { showAnswer.value = !showAnswer.value };

// 計時器 id
let timer: ReturnType<typeof setTimeout> | null = null;
let countdown = ref(0);

watch(showAnswer, (newVal) => {
  if (timer) {
    clearTimeout(timer);
    timer = null;
  }
  if (newVal) {
    countdown.value = 5;
    timer = setInterval(() => {
      countdown.value--;
      if (countdown.value <= 0) {
        showAnswer.value = false;
        clearInterval(timer!);
        timer = null;
      }
    }, 1000);
  } else {
    countdown.value = 0;
  }
});
</script>

<template>
    <div class="question">
        <p>vue 是一個什麼樣的框架</p>
        <p v-show="showAnswer">vue是一套用於建構用戶介面的漸進式框架
            <p v-if="showAnswer">{{ countdown }} 秒</p>
        </p>
        

        <button @click="toggleAnswer()">
            <span>
                {{ label }}
            </span>
        </button>
    </div>
</template>
