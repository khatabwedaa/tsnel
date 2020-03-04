<template>
  <div class="flex items-center justify-center h-screen px-8 py-4" id="app">
    <div class="md:flex items-center container">
      <div class="w-full md:w-1/2">
        <img class="w-4/5" src="../src/assets/img/undraw_dev_productivity_umsq.svg" alt="man typing...">
      </div>
      <div class="w-full text-center text-gray-800 md:w-1/2">
        <type-component></type-component>
      </div>
    </div>
  </div>
</template>

<script>
  import TypeComponent from "./components/TypeComponent";
  export default {
    components: { TypeComponent }
  }
</script>

<style>
  @import "assets/css/tailwind.css";
</style>
