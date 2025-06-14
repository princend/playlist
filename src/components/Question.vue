<script setup lang="ts">
import { computed, ref } from 'vue'

let showAnswer = ref(false);
const label = computed(() => {
   return  showAnswer.value ? '隱藏答案' : '顯示答案'
})

const toggleAnswer= ()=>{showAnswer.value=!showAnswer.value};

</script>

<template>
    <div class="question">
        <p>vue 是一個什麼樣的框架</p>
        <p v-show="showAnswer">vue是一套用於建構用戶介面的漸進式框架</p>

        <button @click="toggleAnswer()">
            <span>
                {{ label }}
            </span>
        </button>
    </div>
</template>
