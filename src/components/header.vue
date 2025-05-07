<script setup>
</script>

<template>
    <div class="header">
        <img src="/img/ダウンロード.png">
    <h1>Vue3をやってみる</h1>
    </div>
</template>
<style scoped>
.header{
    position: relative; /* ← これが重要 */
    margin-top: 10px;
    display: grid; 
    grid-template-columns: 1fr 1fr; 
    grid-template-rows: 1fr; 
    gap: 0px 0px; 
    grid-template-areas: 
    "img . h1"; 
}

.header img{
    grid-area: img;
    
}

.header h1{
    padding-top: 10px;
    padding-right: 15px;
    margin: 0;
    text-align: end;
    /* padding: 0px; */
    grid-area: h1; 
}
</style>
