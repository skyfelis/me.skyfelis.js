<template>
  <section class="sub-group grid gap-5 sm:grid-cols-[12rem_1fr] sm:gap-10">
    <header>
      <h3 class="font-medium text-[#397db8]">{{ title }}</h3>
      <p class="mt-1 text-sm text-slate-500">{{ label }}</p>
    </header>
    <div class="min-w-0">
      <slot />
    </div>
  </section>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  label: string
}>()
</script>

<style scoped>
.sub-group + .sub-group {
  margin-top: 2.5rem;
}
</style>
