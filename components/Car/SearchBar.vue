<script setup>
const city = ref("")
const cityError = ref(false)

const handleSearch = () => {
  if(!city.value) {
    return cityError.value = true
  }
  navigateTo(`/city/${city.value}/car`)
}
</script>


<template>
  <div class="w-full text-2xl rounded-full overflow-hidden drop-shadow-2xl mx-auto bg-white text-slate-800 flex justify-between">
    <input type="text" class="py-3 px-5 rounded-full text-2xl focus:outline-none w-full" placeholder="Search by city..." :class="cityError ? 'border-red-500 border-2 rounded-l-full rounded-r-none' : ''" v-model="city">
    <button type="submit" class="bg-sky-700 hover:bg-sky-900 px-10 text-white" @click="handleSearch">Search</button>
  </div>
</template>
