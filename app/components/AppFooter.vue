<template>
  <footer class="bg-[#28689f] text-white">
    <div class="mx-auto max-w-[1300px] px-6 py-10">
      <!-- 上段：サイト名・コピーライト / トップへ戻る -->
      <div class="flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between">
        <div>
          <a href="#top" class="inline-flex items-center gap-2 text-base tracking-[0.08em] hover:underline">
            <PawIcon class="size-5" />
            me.skyfelis.jp
          </a>
          <p class="mt-1 text-sm text-white/90">&copy; {{ currentYear }} Mayu Kawashima</p>
        </div>
        <a href="#top" class="text-sm text-white/90 hover:text-white hover:underline">Back to top ↑</a>
      </div>

      <!-- 下段：注記 -->
      <div class="mt-6 space-y-1 border-t border-white/25 pt-5 text-xs leading-5 text-white/90">
        <p>プロフィール画像の制作に生成AIを使用しています。</p>
        <p>本サイトにおける内容・発言は個人の見解であり、所属・関係する組織の公式見解を示すものではありません。</p>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>
