<template>
  <section
    :id="id"
    :aria-labelledby="`${id}-heading`"
    :class="[last ? '' : 'border-b border-[#dbe7f0]', tint ? 'bg-[#f4f8fc]' : '']"
  >
    <div class="mx-auto max-w-[1300px] px-6 py-16 sm:py-20">
      <h2 :id="`${id}-heading`" class="text-2xl font-normal text-[#172033]">
        <span class="text-[#397db8]">##</span> {{ title }}
      </h2>
      <div class="mt-10">
        <slot />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
defineProps<{
  id: string
  title: string
  last?: boolean
  /** 淡い水色の背景にする（白と交互に並べてリズムを作る） */
  tint?: boolean
}>()
</script>
