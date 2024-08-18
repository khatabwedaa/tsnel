<script setup>

</script>

<template>
  <div class="flex justify-center items-center px-8 py-4 h-screen" id="app">
    <div class="container items-center md:flex">
      <div class="w-full md:w-1/2">
        <img class="w-4/5" src="../src/assets/images/undraw_dev_productivity_umsq.svg" alt="man typing...">
      </div>
      <div class="w-full text-center text-gray-800 md:w-1/2">
        <type-component></type-component>
      </div>
    </div>
  </div>
</template>
<script setup>
import TypeComponent from '@/components/TypeComponent.vue'
</script>