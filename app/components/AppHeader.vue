<template>
  <header class="sticky top-0 z-10 border-b border-[#dbe7f0] bg-white/90 backdrop-blur">
    <div class="mx-auto flex max-w-[1300px] items-center justify-between gap-4 px-6 py-5">
      <a href="#top" class="inline-flex items-center gap-1.5 text-sm tracking-[0.08em] text-slate-500 transition-colors hover:text-[#397db8]">
        <PawIcon class="size-4 text-[#397db8]" />
        me.skyfelis.jp
      </a>
      <nav aria-label="ページ内ナビゲーション">
        <ul class="flex gap-4 text-sm sm:gap-6">
          <li v-for="item in nav" :key="item.href" :class="item.mobile ? '' : 'hidden sm:block'">
            <a :href="item.href" class="text-[#397db8] transition-colors hover:text-[#28689f]">{{ item.label }}</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup lang="ts">
// 狭い画面では Contact のみ表示（ドメイン名と並べても収まるように）
const nav = [
  { href: "#research", label: "Research", mobile: false },
  { href: "#biography", label: "Biography", mobile: false },
  { href: "#activities", label: "Activities", mobile: false },
  { href: "#contact", label: "Contact", mobile: true },
]
</script>
