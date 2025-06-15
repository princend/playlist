<script setup lang="ts">
const content = `<p>這是一段html</p>`
</script>
<template>
    <article class="text-blue" v-html="content"></article>

</template>