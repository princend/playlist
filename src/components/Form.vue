<script setup lang="ts">
import { ref } from 'vue';

let username = ref("");
const handleInput = (e: { target: { value: any; }; }) => {
    console.log(e.target.value);
    username.value = e.target.value
}

</script>

<template>
    <div>
        <label for="username">用戶名</label>
        <input type="text" id="username" v-model="username">
    </div>
    <div>
        <p style="color: blueviolet;">您輸入的用戶名是:{{ username }}</p>
    </div>

</template>