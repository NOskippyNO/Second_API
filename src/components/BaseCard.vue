<script setup>
const props = defineProps({
  character: {
    type: Object,
    default: () => ({
      _id: -1,
      name: 'Unknown',
      imageUrl: 'https://via.placeholder.com/150',
    }),
  },
})
</script>

<template>
  <RouterLink
    :to="`/character/${props.character._id}`"
    class="name rounded-lg bg-white shadow-lg"
  >
    <img
      class="w-full rounded-t-lg object-cover"
      :src="props.character.imageUrl"
    />
    <div class="p-4">
      <h2 class="text-2xl font-semibold text-gray-800">
        {{ props.character.name }}
      </h2>
    </div>
  </RouterLink>
</template>

<style scoped lang="postcss">
.name {
  @apply cursor-pointer overflow-hidden rounded-md bg-gradient-to-r from-purple-500 to-fuchsia-500 p-8 shadow-md transition-transform duration-300 hover:scale-110 hover:shadow-2xl hover:shadow-slate-800;
}
</style>
