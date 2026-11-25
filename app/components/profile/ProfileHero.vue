<template>
  <!--
    ヒーロー：写真＋キャッチコピー
    - lg 未満：写真（3:2 で切らずに表示）→ その下に白地で文字
    - lg 以上：高さは横幅に比例（12:5）。写真は右側 55% に置き、左端を白へ溶かす。文字は左側の白地に置く
      （写真が暗く、猫が中央付近にいるため、全面に敷くと白いグラデーションが猫の顔にかかる）
  -->
  <div id="top" class="relative isolate overflow-hidden border-b border-[#dbe7f0] bg-[#f4f8fc] lg:flex lg:aspect-[12/5] lg:max-h-[85svh] lg:min-h-[28rem] lg:items-center">
    <picture class="block lg:absolute lg:inset-y-0 lg:right-0 lg:left-[45%] lg:-z-20">
      <source
        type="image/webp"
        srcset="/images/hero-1200.webp 1200w, /images/hero-1600.webp 1600w"
        sizes="(min-width: 1024px) 55vw, 100vw"
      >
      <img
        src="/images/hero-1200.jpg"
        srcset="/images/hero-1200.jpg 1200w, /images/hero-1600.jpg 1600w"
        sizes="(min-width: 1024px) 55vw, 100vw"
        alt=""
        width="1600"
        height="1066"
        fetchpriority="high"
        decoding="async"
        class="aspect-[3/2] w-full object-cover object-[80%_20%] lg:aspect-auto lg:h-full"
      >
    </picture>
    <!-- lg 以上：写真の左端を背景の水色へなめらかにつなぐ（猫は写真の 4 割より右にいるのでかからない） -->
    <div
      class="absolute inset-y-0 left-[45%] -z-10 hidden w-[18%] bg-gradient-to-r from-[#f4f8fc] to-[#f4f8fc]/0 lg:block"
      aria-hidden="true"
    />

    <div class="mx-auto w-full max-w-[1300px] px-6 py-10 sm:py-12 lg:py-0">
      <div class="max-w-xl lg:max-w-md">
        <span class="mb-6 block h-1 w-12 rounded-full bg-[#397db8]" aria-hidden="true" />
        <p class="text-3xl font-normal tracking-tight text-[#172033] sm:text-5xl sm:leading-tight">
          技術と法律の両軸で
        </p>
        <p class="mt-6 leading-8 text-slate-700 sm:text-lg sm:leading-9">
          情報セキュリティを技術と法制度の両面から捉え、安全で信頼できる情報通信基盤について研究しています。
        </p>
      </div>
    </div>
  </div>

  <!-- プロフィール -->
  <section id="profile" aria-labelledby="profile-heading" class="border-b border-[#dbe7f0]">
    <div class="mx-auto grid w-full max-w-[1300px] gap-10 px-6 py-16 sm:py-20 md:grid-cols-2 md:items-center md:gap-16">
      <!-- 左：アイコン・名前 -->
      <div class="flex items-center gap-6 sm:gap-8">
        <div class="size-28 shrink-0 overflow-hidden rounded-full sm:size-32 lg:size-36">
          <img
            src="/images/profile-avatar-288.png"
            srcset="/images/profile-avatar-288.png 2x, /images/profile-avatar-432.png 3x"
            alt="川島雅結のプロフィール画像"
            width="144"
            height="144"
            decoding="async"
            class="size-full object-cover [image-rendering:auto]"
          >
        </div>

        <div>
          <h1 id="profile-heading" class="text-4xl font-normal tracking-tight text-[#172033] sm:text-5xl">
            川島 雅結
          </h1>
          <p class="mt-2 text-xl text-slate-500">KAWASHIMA Mayu</p>
          <p class="mt-1 text-base text-slate-500">
            深瀬みおり<span class="ml-2 text-slate-400">@skyfelis</span>
          </p>
        </div>
      </div>

      <!-- 右：簡単なプロフィール -->
      <div class="border-t border-[#dbe7f0] pt-8 md:border-l md:border-t-0 md:py-2 md:pl-16">
        <p class="leading-8 text-slate-600">
          情報学と法学、経営学などの文理融合分野で、これからのデジタル社会をどう安全に、便利にできるのかを考えています。
        </p>

        <h2 class="mt-8 text-sm text-slate-500">主な専門分野</h2>
        <ul class="mt-2 space-y-1 text-base leading-7 text-slate-800">
          <li class="flex gap-3">
            <span class="text-[#397db8]" aria-hidden="true">・</span>
            <span>情報セキュリティ</span>
          </li>
          <li class="flex gap-3">
            <span class="text-[#397db8]" aria-hidden="true">・</span>
            <span>情報法</span>
          </li>
        </ul>

        <nav class="mt-8" aria-label="主要な外部プロフィール">
          <ul class="space-y-1 text-[#397db8]">
            <li><a href="https://researchmap.jp/skyfelis" target="_blank" rel="noopener noreferrer" class="hover:underline">researchmap ↗</a></li>
            <li><a href="https://orcid.org/0009-0008-4197-3331" target="_blank" rel="noopener noreferrer" class="hover:underline">ORCID ↗</a></li>
            <li><a href="https://github.com/skyfelis" target="_blank" rel="noopener noreferrer" class="hover:underline">GitHub ↗</a></li>
          </ul>
        </nav>
      </div>
    </div>
  </section>
</template>
