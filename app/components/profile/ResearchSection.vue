<template>
  <ProfileSectionBlock id="research" title="Research Interests" tint>
    <div class="max-w-4xl space-y-5 leading-8 text-slate-600">
      <p>
        情報法、セキュリティ法制、プライバシー・データ保護法制などを横断し、情報通信基盤の安全性と信頼性を確保するとともに、一人ひとりが公平にその恩恵を受けられるための技術的・法制度的条件に関心を持っています。
      </p>
      <p>
        また、理工学分野において、多様な人々が能力を発揮しやすい環境の整備に貢献することを目指しています。
      </p>
    </div>

    <div class="mt-12 grid gap-10 sm:grid-cols-3 sm:gap-8">
      <section v-for="group in interestGroups" :key="group.title">
        <header class="border-b border-[#dbe7f0] pb-3">
          <h3 class="font-medium text-[#397db8]">{{ group.title }}</h3>
          <p class="mt-1 text-sm text-slate-500">{{ group.label }}</p>
        </header>
        <ul class="mt-4 space-y-2 text-slate-700">
          <li v-for="item in group.items" :key="item" class="flex gap-3 leading-7">
            <span class="text-[#397db8]" aria-hidden="true">—</span>
            <span>{{ item }}</span>
          </li>
        </ul>
      </section>
    </div>
  </ProfileSectionBlock>
</template>

<script setup lang="ts">
// 文理融合の3分野に分けて表示する
const interestGroups = [
  {
    title: "情報学",
    label: "Informatics",
    items: ["情報セキュリティ", "サイバーセキュリティ", "AIセキュリティ"],
  },
  {
    title: "法学",
    label: "Law",
    items: ["情報法", "セキュリティ法制", "プライバシー・データ保護法制"],
  },
  {
    title: "政策・経営",
    label: "Policy & Management",
    items: ["情報通信政策", "AIガバナンス", "システム監査"],
  },
]
</script>
