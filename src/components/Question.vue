<script setup lang="ts">
import { ref } from 'vue'

let showAnswer = ref(false);

</script>

<template>
    <div class="question">
        <p>vue 是一個什麼樣的框架</p>
        <p v-show="showAnswer">vue是一套用於建構用戶介面的漸進式框架</p>

        <button @click="showAnswer = !showAnswer">
            <span v-if="!showAnswer">
                顯示答案
            </span>
            <span v-else>
                隱藏答案
            </span>
        </button>
    </div>
</template>
