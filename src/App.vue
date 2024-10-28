<script setup lang="ts"></script>

<template>
  <div class="img min-h-screen flex flex-col items-center">
    <RouterView />
  </div>
</template>

<style scoped>
.img {
  /*background: url('https://github.com/cloworm/todo/blob/master/public/images/bg-desktop-dark.jpg?raw=true');*/
  background-image: url('https://github.com/cloworm/todo/blob/master/public/images/bg-desktop-light.jpg?raw=true');
  background-position: top;
  background-repeat: no-repeat;
}
</style>
