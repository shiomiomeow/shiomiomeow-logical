<template>
  <div class="max-w-3xl mx-auto px-6 py-16 space-y-12">
    <h2 class="text-4xl font-black italic uppercase text-blue-600">Guidelines</h2>
    
    <section v-for="section in guidelines" :key="section.title" class="space-y-4">
      <h3 class="text-xl font-bold text-slate-800 flex items-center gap-2">
        <span class="w-2 h-6 bg-blue-600 rounded-full"></span>
        {{ section.title }}
      </h3>
      <p class="text-slate-600 text-sm leading-relaxed whitespace-pre-wrap">{{ section.content }}</p>
    </section>
  </div>
</template>

<script setup lang="ts">
const guidelines = [
  { title: '二次創作について', content: 'ファンアートは大歓迎です！ハッシュタグ #みおあーと をつけて投稿していただければ幸いです。公序良俗に反するもの、政治・宗教的利用はご遠慮ください。' },
  { title: '切り抜き動画について', content: '収益化設定をしていない動画に限り、自由に切り抜いていただけます。概要欄に元動画のURLを必ず記載してください。' },
  { title: 'プライバシーポリシー', content: '当サイトでは、お問い合わせ時に提供いただいた個人情報を、回答以外の目的で使用することはありません。' }
]
</script>