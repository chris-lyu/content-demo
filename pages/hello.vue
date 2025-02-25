<script setup lang="ts">
const { data: hello } = await useAsyncData(() => queryCollection('content').path('/hello').first())

useSeoMeta({
  title: hello.value?.title,
  description: hello.value?.description
})
</script>

<template>
  <ContentRenderer v-if="hello" :value="hello" />
  <div v-else>hello not found</div>
</template>
