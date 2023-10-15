<script setup>
const props = defineProps({
  car: Object
})
</script>

<template>
  <div class="mt-10">
      <NuxtImg :src="car.url" class="w-full" alt="car" />
      <h1 class="text-4xl mt-10">{{ car.name }}</h1>
      <div class="text-slate-500 flex justify-between text-lg mt-3 border-b pb-5 items-center">
        <div class="flex items-center">
          <p class="mr-2">{{ car.seats }} seats</p>
          <p class="mr-2"> | </p>
          <p class="mr-2">{{ car.miles }} miles</p>
        </div>
        <div>
          <p class="font-bold text-2xl">${{ car.price }}</p>
        </div>
      </div>
    </div>
</template>
