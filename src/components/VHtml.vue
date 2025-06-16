<script setup lang="ts">
import { computed, ref } from 'vue';

const content = `<p>這是一段html</p>`
const list = ref([1, 2, 3])


const appendValue = computed(() => {
    list.value.push(list.value.length + 1)
})

const attr = ref('placeholder')
const value = ref('test')

const props = defineProps<{
    title: string,
    content?: string
}>()
</script>
<template>
    <div class="text-blue">
        <h2>{{ props.title }}</h2>
        <article class="text-blue" v-html="props?.content||content"></article>
        <p v-once>list 初始長度 {{ list.length }}</p>
        <button @click="() => appendValue"> 增加列表</button>
        <div>list:{{ list }}</div>

        <input type="text" name="" id=" " :[attr]="value">

    </div>
</template>