<script setup>
import { ref,computed } from 'vue'


// 切り替え用のフラグ
const isA = ref(true)

// 切り替え関数
function toggle() {
  isA.value = !isA.value
}

// 表示するコンポーネントを決定
const currentComponent = computed(() => (isA.value ? conponent1 : conponent2))

</script>

<template>
    <div>
        
    </div>
</template>
<style scoped>

</style>
