<script setup>
import heartFilled from "@/assets/heartFilled.png";
import heartOutline from "@/assets/heartOutline.png";

const props = defineProps({
  car: Object,
  favored: Boolean,
});

const emit = defineEmits(["favor"]);
</script>

<template>
   <div class="shadow border w-full overflow-hidden relative mb-5 cursor-pointer h-[200px]">
     <img
      class="absolute w-7 right-5 top-2 z-20"
      :src="favored ? heartFilled : heartOutline"
      alt="hearts"
      @click="emit('favor', car.id)" />
      <div class="flex h-full" @click="navigateTo(`/car/${car.name}-${car.id}/`)">
        <NuxtImg :src="car.url" alt="land rover" class="object-contain w-[300px] h-full" />
        <div class="p-4 flex flex-col">
          <div>
            <h1 class="text-2xl text-blue-400">{{ car.make }}</h1>
            <p class="text-gray-700">{{ car.description }}</p>
          </div>
          <h1 class="mt-auto text-xl">${{ car.price }}</h1>
        </div>
      </div>
  </div>
</template>
