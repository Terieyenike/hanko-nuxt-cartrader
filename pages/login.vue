<script setup>
definePageMeta({
  layout: "custom",
});

function afterLogin() {
 navigateTo("/profile");
}
</script>

<template>
  <hanko-auth @onAuthFlowCompleted="afterLogin()" />
</template>
