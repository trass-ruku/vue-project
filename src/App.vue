<script setup>
// import { ref,computed } from 'vue'
import { ref, onMounted, onUnmounted } from 'vue'
import Header from './components/header.vue'
import Menu from './components/Menu.vue'
import Hamburger from './components/hamburger.vue'
// import conponent1 from './components/raiout1.vue'
// import conponent2 from './components/raiout2.vue'

const isMobile = ref(false)
const showMenu = ref(false)

const checkWidth = () => {
  isMobile.value = window.innerWidth <= 768
}
const toggleMenu = () => {
  showMenu.value = !showMenu.value
}

onMounted(() => {
  checkWidth()
  window.addEventListener('resize', checkWidth)
})
onUnmounted(() => {
  window.removeEventListener('resize', checkWidth)
})

// 表示するコンポーネントを決定
// const currentComponent = computed(() => (isA.value ? conponent1 : conponent2))

</script>

<template>
  <header class="header">
    <Header />
    <!-- スマホだけ表示されるハンバーガー -->
</header>
  <div class="controller-rayout">
    <div class="layout">
      <Menu v-if="!isMobile || showMenu" />
      <Hamburger v-if="isMobile" @toggle="toggleMenu" />
    </div>
  <div class="main-container">
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

.controller-rayout{
  flex: 1;
  display: flex;
  gap: 20px;
  overflow: hidden;
}
</style>
