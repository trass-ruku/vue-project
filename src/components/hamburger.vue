<template>
    <button class="hamburger" @click="$emit('toggle')">☰</button>
</template>

<style scoped>
    .hamburger {
        font-size: 2em;
        background: none;
        border: none;
        position: absolute;
        top: 10px;
        left: 10px;
        z-index: 1000;
    }
</style>