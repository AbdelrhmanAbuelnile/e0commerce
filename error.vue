<template>
  <div class="w-full h-screen flex justify-center items-center">
    <div
      class="p-10 rounded-3xl flex flex-col justify-center items-center w-3/4 md:w-2/4 bg-Grayish"
    >
      <div
        class="h-2/4 w-3/4 md:w-2/4 md:h-2/6 lg:w-1/4 lg:h-2/4 mx-auto text-center"
      >
        <p class="mt-7 text-5xl md:text-7xl font-bold">{{ error.statusCode }}</p>
        <p class="mt-7 text-3xl md:text-6xl">Ooops.</p>
        <p class="mt-7">{{ error.message }}</p>
        <button class="my-7 bg-Primary rounded-md text-white text-xl md:text-3xl p-2 hover:bg-Accent hover:scale-105 duration-300" @click="handleClearError">
          Go Home...
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps(["error"]);

const handleClearError = () => clearError({ redirect: "/" });
</script>
