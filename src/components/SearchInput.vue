<script setup lang="ts">
import { computed, ref } from 'vue';

const props = defineProps<{ modelValue: string }>()
const emit = defineEmits<{ e: 'update:modelValue', v: any }>()
const value = computed({ get: () => props.modelValue, set: (val: string) => emit })
</script>

<template>
    <input v-model="value" />
</template>