<template>
  <ProfileSectionBlock id="contact" title="Contact" last>
    <ProfileSubGroup title="Email" label="お問い合わせ">
      <p class="max-w-xl leading-8 text-slate-600">
        研究・執筆・発表などに関するお問い合わせは、メールよりお願いいたします。
      </p>
      <a href="mailto:contact@skyfelis.jp" class="mt-4 inline-block break-all text-[#397db8] hover:underline">
        contact@skyfelis.jp
      </a>
      <p class="mt-4 text-sm leading-7 text-slate-500">
        内容によっては、お返事までお時間をいただく場合があります。
      </p>
    </ProfileSubGroup>

    <ProfileSubGroup title="Links" label="外部リンク">
      <ul class="grid border-t border-[#dbe7f0] sm:grid-cols-2 sm:gap-x-8">
        <li v-for="link in links" :key="link.name" class="border-b border-[#dbe7f0]">
          <a :href="link.url" target="_blank" rel="noopener noreferrer" class="group flex items-center justify-between gap-6 py-5">
            <span class="min-w-0">
              <span class="block text-slate-800 transition-colors group-hover:text-[#397db8]">{{ link.name }}</span>
              <span class="mt-1 block text-sm text-slate-500">{{ link.description }}</span>
            </span>
            <span class="text-[#397db8]" aria-hidden="true">↗</span>
          </a>
        </li>
      </ul>
    </ProfileSubGroup>
  </ProfileSectionBlock>
</template>

<script setup lang="ts">
const links = [
  { name: "Blog", description: "技術・日々の記録", url: "https://blog.skyfelis.jp/" },
  { name: "researchmap", description: "研究者プロフィール・研究業績", url: "https://researchmap.jp/skyfelis" },
  { name: "ORCID", description: "0009-0008-4197-3331", url: "https://orcid.org/0009-0008-4197-3331" },
  { name: "GitHub", description: "@skyfelis", url: "https://github.com/skyfelis" },
  { name: "LinkedIn", description: "Professional profile", url: "https://www.linkedin.com/in/mayu2664/" },
  { name: "X / Twitter", description: "@mayu2664", url: "https://x.com/mayu2664" },
  { name: "Facebook", description: "Social profile", url: "https://www.facebook.com/people/%E5%B7%9D%E5%B3%B6%E9%9B%85%E7%B5%90/pfbid0TL8xS4WyFD2oDofAxCR94tRHkpueqoTCVSuA1N94Q27PP2XzFBMWmQUNUfhArixyl/" },
]
</script>
