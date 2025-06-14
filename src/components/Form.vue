<script setup lang="ts">
import { ref } from 'vue';

let username = ref("");
let gender = ref("");
const handleInput = (e: { target: { value: any; }; }) => {
    console.log(e.target.value);
    username.value = e.target.value
}

</script>

<template>
    <div style="color: blue;">
        <label for="username">用戶名</label>
        <input type="text" id="username" v-model="username">
        <br>
        性別:<input type="radio" name="gender" id="gender" value="male" v-model="gender">男
        <input type="radio" name="gender" id="gender" value="female" v-model="gender">女

    </div>
    <div>
        <p style="color: blueviolet;">您輸入的用戶名是:{{ username }}</p>
        <p style="color: blueviolet;">您的性別是:{{ gender }}</p>
    </div>

</template>