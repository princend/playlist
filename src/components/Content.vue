<script setup lang="ts">
import { ref, computed } from 'vue'

// defineProps({
//   msg: String,
// })

// const count = ref(0)

const playList = ref([
    {
        name: '記得',
        singer: '張惠妹',
        album: '記得',
        complete: false,
    },
    {
        name: '黑色幽默',
        singer: '周杰倫',
        album: '范特西',
        complete: false,
    },
    {
        name: '失落沙洲',
        singer: '蘇打綠',
        album: '蘇打綠',
        complete: false,
    },

])

const search = ref('')

const filteredPlayList = computed(() => {
    return playList.value.filter((item) => item.name.includes(search.value))
})

const url = 'https://www.google.com'
let showAnswer=ref(false);

</script>

<template>
    <button v-on:click="showAnswer= !showAnswer">按鈕</button>
    <p v-show="showAnswer">安安</p>
    <h1>播放列表</h1>
    <input type="text" placeholder="请输入歌曲名称" class="searh" v-model="search"   />
    <ul>
        <p v-if="filteredPlayList.length === 0"> 沒有找到歌曲 </p>
        <li v-for="item in filteredPlayList" :key="item.name" v-else>


            <input type="checkbox" v-model="item.complete" />
            <span>{{ item.name }}</span>
            <!-- <span>{{ item.singer }}</span>
            <span>{{ item.album }}</span> -->
        </li>

    </ul>
</template>
