<script setup lang="ts">
import { MoonIcon, SunIcon } from '@heroicons/vue/24/solid'

const isDark: boolean = true
</script>

<template>
  <div v-bind:class="isDark ? 'dark' : ''" class="wrapper">
    <div class="btn-wrapper">
      <div class="toggle-btn flex items-center justify-center w-full my-4">
        <label
          for="toggle"
          class="flex items-center justify-center cursor-pointer"
        >
          <div class="relative">
            <input type="checkbox" id="toggle" class="sr-only" />
            <div class="block bg-gray-600 w-14 h-8 rounded-full"></div>
            <div
              class="dot absolute left-1 top-1 bg-black w-6 h-6 flex items-center justify-center rounded-full transition"
            >
              <!-- usar directiva v-if  para mostrar el icono de luna o sol -->
              <MoonIcon v-if="isDark" class="w-4 h-4 text-white" />
              <SunIcon
                v-if="!isDark"
                class="w-full h-full text-yellow-500 pl-1"
              />
            </div>
          </div>

          <!-- cambiar el texto segun sea Light o Dark mode -->
          <div
            v-bind:class="isDark ? 'dark' : ''"
            class="label-text ml-2 font-medium"
          >
            Light-mode
          </div>
        </label>
      </div>
    </div>
    <div
      v-bind:class="isDark ? 'dark' : ''"
      class="img min-h-screen flex flex-col items-center transition"
    ></div>
    <div class="todo flex-1 lg:w-2/3 xl:w-2/5 w-full px-7">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  height: 100vh;
  width: 100vw;
  background: #fff;
}

.wrapper.dark {
  background: #434343;
}
.img {
  /*background: url('https://github.com/cloworm/todo/blob/master/public/images/bg-desktop-dark.jpg?raw=true');*/
  background-image: url('https://github.com/cloworm/todo/blob/master/public/images/bg-desktop-light.jpg?raw=true');
  background-position: top;
  background-repeat: no-repeat;
}

.img.dark {
  background: url('https://github.com/cloworm/todo/blob/master/public/images/bg-desktop-dark.jpg?raw=true');
  background-position: top;
  background-repeat: no-repeat;
}

.btn-wrapper {
  position: absolute;
  right: 16px;
}

input:checked ~ .dot {
  transform: translateX(100%);
  background-color: rgb(77, 148, 255);
}

.label-text {
  color: black;
}

.label-text.dark {
  color: white;
}

.todo {
  position: fixed;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
}
</style>
