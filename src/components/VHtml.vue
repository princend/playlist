<script setup lang="ts">
import { ref } from 'vue';

const content = `<p>這是一段html</p>`
const list = ref([1, 2, 3])
</script>
<template>
    <div class="text-blue">
        <article class="text-blue" v-html="content"></article>
        <p v-once>list 初始長度 {{ list.length }}</p>
    </div>
</template>