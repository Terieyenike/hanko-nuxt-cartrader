<script setup>
const route = useRoute()
// const { cars } = useCars()

const {data: car} = await useFetchCar(route.params.id)

const { toTitleCase } = useUtilities()

useHead({
  title: toTitleCase(route.params.name)
})

// const car = computed(() => {
//   return cars.find((c) => {
//     return c.id === parseInt(route.params.id)
//   })
// })

if (!car.value) {
  throw createError({
    statusCode: 404,
    message: `Car with ID of ${route.params.id} does not exist`,
  });
}

definePageMeta({
  layout: "custom"
})
</script>

<template>
  <div v-if="car">
    <car-detail-hero :car="car" />
    <car-detail-attributes :features="car.features" />
    <car-detail-description :description="car.description" />
    <car-detail-contact />
  </div>
</template>
