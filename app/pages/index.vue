<template>
    <main>
        <ProfileHero />
        <ProfileResearchSection />
        <ProfileBiographySection />
        <ProfileActivitiesSection />
        <ProfileContactSection />
    </main>
</template>

<script setup lang="ts">
const siteUrl = "https://me.skyfelis.jp"
const pageTitle = "川島 雅結（KAWASHIMA Mayu）｜情報セキュリティ・情報法"
const pageDescription =
    "情報セキュリティを技術と法制度の両面から捉え、安全で信頼できる情報通信基盤について研究する川島雅結のプロフィールサイトです。"
const ogImage = `${siteUrl}/images/profile.png`

useSeoMeta({
    title: pageTitle,
    description: pageDescription,
    ogTitle: pageTitle,
    ogDescription: pageDescription,
    ogType: "website",
    ogUrl: siteUrl,
    ogSiteName: "me.skyfelis.jp",
    ogLocale: "ja_JP",
    ogImage,
    ogImageAlt: "川島雅結のプロフィール画像",
    ogImageType: "image/png",
    ogImageWidth: 1254,
    ogImageHeight: 1254,
    twitterCard: "summary",
    twitterTitle: pageTitle,
    twitterDescription: pageDescription,
    twitterImage: ogImage,
    twitterImageAlt: "川島雅結のプロフィール画像",
})

useHead({
    link: [{ rel: "canonical", href: siteUrl }],
})
</script>
