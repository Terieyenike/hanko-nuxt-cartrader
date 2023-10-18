<script setup>
// const hanko = useHanko()
// const { email } = hanko.user.getCurrent()
</script>

<template>
  <header class="sticky top-0 z-50 flex justify-between items-center space-x-1 border-b bg-white p-4 shadow-md">
    <NuxtLink to="/" class="text-3xl font-mono">cartrader</NuxtLink>
    <div class="flex items-center">
      <NuxtLink to="/profile/listings" class="mr-5">profile</NuxtLink>
      <p class="cursor-pointer"><LogoutButton /></p>
    </div>
  </header>
</template>
