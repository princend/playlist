<script setup lang="ts">
import { ref } from 'vue';

let username = ref("");
let gender = ref("");
const submitEvent = (e:any) => {
   console.log(e);
}

</script>

<template>
    <form @submit.prevent="submitEvent">
    <div style="color: blue;">
        <label for="username">用戶名</label>
        <input type="text" id="username" v-model="username">
        <br>
        性別:<input type="radio" name="gender" id="gender" value="male" v-model="gender">男
        <input type="radio" name="gender" id="gender" value="female" v-model="gender">女

    </div>
    <button type="submit">提交</button>
</form>
    <div>
        <p style="color: blueviolet;">您輸入的用戶名是:{{ username }}</p>
        <p style="color: blueviolet;">您的性別是:{{ gender }}</p>
    </div>

</template>