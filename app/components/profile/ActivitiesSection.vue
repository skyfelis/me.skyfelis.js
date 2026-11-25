<template>
  <ProfileSectionBlock id="activities" title="Activities" tint>
    <!-- 業績：成果物（新しい順。論文が出たら type: "論文" で追加する） -->
    <ProfileSubGroup title="業績" label="Publications & Talks">
      <ul class="divide-y divide-[#dbe7f0] border-y border-[#dbe7f0]">
        <li
          v-for="item in publications"
          :key="item.name"
          class="grid gap-2 py-6 sm:grid-cols-[7rem_1fr] sm:gap-6"
        >
          <p class="leading-7 text-slate-500 tabular-nums">{{ item.date }}</p>
          <div>
            <div class="flex flex-wrap items-baseline gap-x-3 gap-y-1">
              <span class="rounded-sm bg-[#e6f0f8] px-2 py-0.5 text-xs text-[#28689f]">{{ item.type }}</span>
              <a
                v-if="item.url"
                :href="item.url"
                target="_blank"
                rel="noopener noreferrer"
                class="leading-7 text-slate-800 transition-colors hover:text-[#397db8] hover:underline"
              >{{ item.name }} ↗</a>
              <span v-else class="leading-7 text-slate-800">{{ item.name }}</span>
            </div>
            <p class="mt-2 leading-7 text-slate-500">{{ item.description }}</p>
          </div>
        </li>
      </ul>
    </ProfileSubGroup>

    <!-- 活動：継続している取り組み -->
    <ProfileSubGroup title="活動" label="Projects & Community">
      <ul class="divide-y divide-[#dbe7f0] border-y border-[#dbe7f0]">
        <li
          v-for="item in activities"
          :key="item.name"
          class="grid gap-2 py-6 sm:grid-cols-[7rem_1fr] sm:gap-6"
        >
          <p class="text-sm leading-7 text-slate-500">{{ item.type }}</p>
          <div>
            <a
              v-if="item.url"
              :href="item.url"
              target="_blank"
              rel="noopener noreferrer"
              class="leading-7 text-slate-800 transition-colors hover:text-[#397db8] hover:underline"
            >{{ item.name }} ↗</a>
            <p v-else class="leading-7 text-slate-800">{{ item.name }}</p>
            <p class="mt-2 leading-7 text-slate-500">{{ item.description }}</p>
          </div>
        </li>
      </ul>
    </ProfileSubGroup>
  </ProfileSectionBlock>
</template>

<script setup lang="ts">
interface Item {
  type: string
  name: string
  description: string
  url?: string
}

interface Publication extends Item {
  /** "YYYY-MM"、または継続的なものは "継続中" */
  date: string
}

const publications: Publication[] = [
  {
    date: "2026-08",
    type: "書籍",
    name: "セキスペ大石泉と学ぶ組織の情報セキュリティ論",
    description: "『学術アイドルマスター 合同 Vol.3』所収、pp.55–68、学術アイドルマスター合同準備会、2026年8月16日。分担執筆（査読なし）。",
    url: "https://researchmap.jp/skyfelis/books_etc/54568449",
  },
  {
    date: "継続中",
    type: "発表",
    name: "技術コミュニティでの発表",
    description: "技術系イベントやコミュニティにおいて、LTなどの発表を行っています。",
  },
]

const activities: Item[] = [
  {
    type: "プロジェクト",
    name: "Virtual YouTuber『汐猫みお』の企画・運営",
    description: "情報セキュリティ、情報法、プログラミングなどをテーマに、配信・動画制作・Webサイト運営を行っています。",
    url: "https://cats.skyfelis.jp/",
  },
  {
    type: "コミュニティ",
    name: "学会・研究コミュニティへの参加",
    description: "研究会や学術イベントを通じて知見を深めています。",
  },
]
</script>
