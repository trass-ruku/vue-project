<script setup>
import { ref } from 'vue'

defineProps({
    msg: String,
})

const count = ref(0)
</script>

<template >
    <button id="button-design">テスト作成</button>
</template>

<style>
#button-design {
    margin: 0 auto;
    border-radius: 2em;
    border-color: chocolate;
    padding: 10px;
    background-color: chocolate;
    color: white;
}
</style>
