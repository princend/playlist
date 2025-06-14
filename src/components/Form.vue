<script setup lang="ts">
import { computed, ref } from 'vue';

let username = ref("");
let gender = ref("");
const submitEvent = (e: any) => {
    console.log(e);
}
const color = ref("blue");
const fontSize = ref(16);

const divStyle = computed(()=> 
    ({
        color: color.value,
        fontSize: fontSize.value + 'px'
    })

)
</script>

<template>
    <form @submit.prevent="submitEvent">
        <div :style="divStyle">
            <label for="username">用戶名</label>
            <input type="text" id="username" v-model="username">
            <br>
            性別:<input type="radio" name="gender" id="gender" value="male" v-model="gender">男
            <input type="radio" name="gender" id="gender" value="female" v-model="gender">女

        </div>
        <button type="submit">提交</button>
    </form>
    <button @click="fontSize += 1">A</button>
    <button @click="fontSize -= 1">a</button>
    <div>
        <p style="color: blueviolet;">您輸入的用戶名是:{{ username }}</p>
        <p style="color: blueviolet;">您的性別是:{{ gender }}</p>
    </div>

</template>