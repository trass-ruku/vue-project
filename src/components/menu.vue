<template>
  <nav class="menu">
    <ul>
      <li>リスト1</li>
      <li>リスト2</li>
      <li>リスト3</li>
      <li>リスト4</li>
    </ul>
  </nav>
</template>

<style scoped>
.menu {
  width: 200px;
  background-color: #00FFFF;
  padding: 20px;
  color: white;
  position: absolute;
  top: 60px; /* ヘッダー下 */
  left: 0;
  z-index: 500; /* ハンバーガーより下 */
}
/* .menu ul {
  list-style: disc;
  padding-left: 1.5em;
} */

@media (min-width: 769px) {
  .menu {
    position: static; /* PCでは通常のフローに戻す */
    z-index: auto;
    width: 200px;
  }
}
</style>