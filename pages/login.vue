<script setup>
import "~/assets/css/styles.css"

definePageMeta({
  layout: "custom",
});

function afterLogin() {
 navigateTo("/user");
}
</script>

<template>
  <hanko-auth @onAuthFlowCompleted="afterLogin()" />
</template>
