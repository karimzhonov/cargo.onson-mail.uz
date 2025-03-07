<template>
  <NuxtLayout>
    <NuxtPage/>
  </NuxtLayout>
</template>
<script setup lang="ts">
useHead({
  title: 'Onson Mail Cargo',
  meta: [
    { name: 'description', content: 'Cargo, turism and consalting' },
    { charset: 'utf-8' },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
  ],
  link: [
    { rel: 'icon', type: 'image/png', href: '/logo.png' }
  ]
})
</script>