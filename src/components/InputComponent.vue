<script setup lang="ts"></script>

<template>
  <div class="relative group border-dark">
    <div class="absolute top-3 sm:top-4 left-5">
      <div class="relative">
        <input
          type="ckeckbox"
          class="form-checkbox border rounded-full focus:ouline-none h-6 w-6 cursor-pointer transition ease-linear"
        />
        <!-- SI ES TAREA COMPLETA CON V-IF -->
        <img
          src="@/assets/icons/check-circle.svg"
          alt="Checkbox image for checkbox input"
          class="absolute top-0 left-0.2 pointer-events-none"
        />
      </div>
    </div>
    <form>
      <input
        type="text"
        class="sm:text-base overflow-ellipsis w-full focus:outline-none py-4 sm:py-4.5 pr-8 pl-14 sm:pl-16 cursor-pointer transition ease-linear"
      />
    </form>
  </div>
</template>
