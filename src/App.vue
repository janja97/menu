
<template>
  <div class="menu">
    <header class="p-2 d-flex align-items-center">
      <img src="/public/logo/logo.png" class="logo-img" alt="">
      <h4 class="p-0 m-0">Caffe Bar Raba</h4>
    </header>
    <main>
      <Main />
    </main>
  </div>
 
</template>
<script setup>

import Main from './components/Main.vue'
</script>


<style scoped>
h4{
  color: #3C2C32;
  font-weight: 700;

}
.logo-img {
  width: auto;
  height: 40px;
}
</style>
