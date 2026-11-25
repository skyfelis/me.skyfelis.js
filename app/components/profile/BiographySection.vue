<template>
  <ProfileSectionBlock id="biography" title="Biography">
    <ProfileSubGroup title="Education" label="学歴">
      <ol class="border-l border-[#397db8]">
        <li
          v-for="school in education"
          :key="`${school.period}-${school.program}`"
          class="education-item"
        >
          <div class="education-date border-b border-[#9fc8e8] text-slate-500">
            {{ school.period }}
          </div>

          <div class="education-marker rounded-full bg-[#397db8]" aria-hidden="true" />

          <div class="education-details">
            <h4 class="font-medium text-[#172033]">{{ school.institution }}</h4>
            <p class="text-slate-600">{{ school.program }}</p>
            <p class="text-slate-600">{{ school.status }}</p>
            <p v-if="school.note" class="text-slate-500">{{ school.note }}</p>
          </div>
        </li>
      </ol>
    </ProfileSubGroup>

    <ProfileSubGroup title="Memberships" label="所属学会・団体">
      <ul class="divide-y divide-[#dbe7f0] border-y border-[#dbe7f0]">
        <li v-for="membership in memberships" :key="membership.name" class="grid gap-1 py-5 lg:grid-cols-[1fr_1.4fr] lg:gap-8">
          <span class="text-slate-800">{{ membership.name }}</span>
          <span class="text-sm leading-6 text-slate-500">{{ membership.english }}</span>
        </li>
      </ul>
    </ProfileSubGroup>
  </ProfileSectionBlock>
</template>

<script setup lang="ts">
const education = [
  {
    period: "2026/4 - 現在",
    institution: "放送大学",
    program: "大学院文化科学研究科",
    status: "（修士課程）修士選科生",
    note: "2026/10 - 2027/3 休学",
  },
  {
    period: "2026/4 - 現在",
    institution: "放送大学",
    program: "教養学部 教養学科 社会と産業コース",
    status: "全科履修生",
    note: "2026/10 - 2027/3 休学",
  },
  {
    period: "2021/4 - 2026/3",
    institution: "サイバー大学",
    program: "IT総合学部 IT総合学科",
    status: "学士（IT総合学）",
    note: "2023/4 - 2024/3 休学",
  },
  {
    period: "2018/4 - 2021/3",
    institution: "学校法人角川ドワンゴ学園 N高等学校",
    program: "普通科",
    status: "卒業",
  },
]

const memberships = [
  { name: "情報処理学会", english: "Information Processing Society of Japan (IPSJ)" },
  { name: "電子情報通信学会", english: "Institute of Electronics, Information and Communication Engineers (IEICE)" },
  { name: "人工知能学会", english: "Japanese Society for Artificial Intelligence (JSAI)" },
  { name: "一般社団法人 MyData Japan", english: "MyData Japan" },
]
</script>

<style scoped>
.education-item {
  margin-block: 0.75rem;
}

.education-item:first-child {
  margin-top: 0;
}

.education-date,
.education-details {
  padding-left: 1rem;
  line-height: 1.75rem;
}

.education-marker {
  width: 0.5rem;
  height: 0.5rem;
  margin-top: -0.25rem;
  margin-left: -0.25rem;
}
</style>
