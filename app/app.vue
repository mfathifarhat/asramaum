<script setup>
useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - Asrama UM` : 'Asrama UM'
  },
})
</script>

<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtLayout>
      <NuxtPage class="bg-zinc-200" />
    </NuxtLayout>
  </div>
</template>
