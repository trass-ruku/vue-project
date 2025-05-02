<script setup>
import { ref,computed } from 'vue'
import conponent1 from './components/raiout1.vue'
import conponent2 from './components/raiout2.vue'

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
  <header class="header">
  <h1>vue3をやってみるよ</h1>
</header>
  <div class="controller-rayout">
    <div class="sub-container">
      <ul class="space-y-">
        <li class="bg-gray-700 text-white p-4 rounded hover:bg-gray-600 cursor-pointer">リスト1</li>
        <li class="bg-gray-700 text-white p-4 rounded hover:bg-gray-600 cursor-pointer">リスト2</li>
        <li class="bg-gray-700 text-white p-4 rounded hover:bg-gray-600 cursor-pointer">リスト3</li>
        <li class="bg-gray-700 text-white p-4 rounded hover:bg-gray-600 cursor-pointer">リスト4</li>
      </ul>
    </div>
  <div class="main-container">
    <button @click="toggle" class="bg-blue-600 text-white px-6 py-2 rounded hover:bg-blue-700 transition">コンポーネント切り替え</button>
    <component :is="currentComponent" />
    <!-- <testButton></testButton> -->
  </div>
</div>
</template>
<style scoped>
.header{
  padding-left: 20px;
}

.main-container{
  flex: 1;
  background: white;
  padding: 20px;
  border-radius: 8px;
  border: solid darkgray;
  overflow-y: auto;
  margin: 20px;
}

.sub-container{
  width: 200px;
}

.sub-container ul{
  padding-left: 20px;
  position: relative;
}

.sub-container li{
  border-left: solid 6px white;
  margin-bottom: 3px;
  line-height: 1.5;
  padding: 1.5em;
  list-style-type: none!important;
}

.controller-rayout{
  flex: 1;
  display: flex;
  gap: 20px;
  overflow: hidden;
}
</style>
