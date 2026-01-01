<template>
    <div>
        <section class="pt-16 pb-24 px-6 bg-gradient-to-b from-white to-blue-50">
            <div class="max-w-6xl mx-auto flex flex-col lg:flex-row items-center gap-16">
                <div class="flex-1 relative order-2 lg:order-1">
                    <div class="relative w-full aspect-[4/5] max-w-sm mx-auto">
                        <div class="absolute inset-0 bg-blue-600 rounded-3xl rotate-3 opacity-5"></div>
                        <img src="" alt="汐猫みお"
                            class="relative rounded-3xl shadow-2xl w-full h-full object-cover border-8 border-white" />
                    </div>
                </div>

                <div class="flex-1 space-y-8 order-1 lg:order-2">
                    <div class="space-y-2">
                        <h2 class="text-xl font-black italic text-blue-600 tracking-widest">LOGICAL MODE</h2>
                        <h1 class="text-6xl md:text-7xl font-black italic text-slate-900 tracking-tighter">汐猫みお</h1>
                        <p class="text-slate-400 font-bold tracking-[0.2em] uppercase">Shioneko Mio</p>
                    </div>

                    <div class="grid grid-cols-2 gap-4">
                        <div v-for="tag in profileTags" :key="tag.label"
                            class="bg-white p-3 rounded-xl border border-blue-50 shadow-sm">
                            <p class="text-[10px] font-bold text-blue-400 uppercase mb-1">{{ tag.label }}</p>
                            <p class="text-sm font-bold text-slate-700">{{ tag.value }}</p>
                        </div>
                    </div>

                    <p class="text-slate-600 leading-relaxed font-medium">
                        論理的に遊び、エンターテインメントを構築する。<br>
                        配信という舞台で情報の深淵を読み解く、青い世界の住人です。
                    </p>
                </div>
            </div>
        </section>

        <section id="about" class="py-24 px-6 bg-slate-50/50 overflow-hidden">
            <div class="max-w-6xl mx-auto">
                <div class="text-center mb-16">
                    <h3 class="text-3xl font-black italic text-slate-900 tracking-tighter uppercase">Profile</h3>
                    <div class="w-12 h-1 bg-gradient-to-r from-blue-600 to-cyan-400 mx-auto mt-2 rounded-full"></div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">

                    <div class="lg:col-span-2 space-y-8">

                        <div class="bg-white rounded-3xl p-8 shadow-sm border border-slate-100">
                            <div class="flex items-center gap-2 mb-8 border-l-4 border-blue-600 pl-4">
                                <h4 class="font-black text-slate-800 uppercase tracking-widest text-lg">基本情報 / Status
                                </h4>
                            </div>

                            <div class="grid grid-cols-1 md:grid-cols-2 gap-x-1s gap-y-6">
                                <div v-for="item in fullProfile" :key="item.label" class="space-y-1">
                                    <p
                                        class="text-[10px] font-bold text-blue-400 uppercase tracking-widest flex items-center gap-2">
                                        <span class="w-1.5 h-1.5 bg-blue-600 rounded-full"></span>
                                        {{ item.label }}
                                    </p>
                                    <p class="text-sm font-bold text-slate-700 pl-3.5">{{ item.value }}</p>
                                </div>
                            </div>
                        </div>

                        <div class="bg-white rounded-3xl p-8 shadow-sm border border-slate-100">
                            <div class="flex items-center gap-2 mb-8 border-l-4 border-blue-600 pl-4">
                                <h4 class="font-black text-slate-800 uppercase tracking-widest text-lg">技術スタック / Tech
                                    Stack</h4>
                            </div>

                            <div class="space-y-8">
                                <div class="space-y-4">
                                    <p class="text-[10px] font-bold text-slate-400 uppercase tracking-[0.2em]">
                                        Programming Languages</p>
                                    <div class="flex flex-wrap gap-2">
                                        <span v-for="lang in techFavs.languages" :key="lang"
                                            class="px-4 py-1.5 bg-blue-50 text-blue-600 font-mono text-xs rounded-full font-bold border border-blue-100">
                                            {{ lang }}
                                        </span>
                                    </div>
                                </div>
                                <div class="space-y-4">
                                    <p class="text-[10px] font-bold text-slate-400 uppercase tracking-[0.2em]">Favorite
                                        OS</p>
                                    <div class="flex flex-wrap gap-2">
                                        <span v-for="os in techFavs.os" :key="os"
                                            class="px-4 py-1.5 bg-slate-900 text-emerald-400 font-mono text-xs rounded-lg border border-slate-700 shadow-lg shadow-emerald-900/10">
                                            > {{ os }}
                                        </span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="space-y-8">
                        <div class="bg-white p-4 rounded-3xl shadow-sm border border-slate-100">
                            <div class="aspect-[3/4] rounded-2xl overflow-hidden bg-slate-50">
                                <img src="" alt="汐猫みお" class="w-full h-full object-cover" />
                            </div>
                        </div>

                        <div class="bg-white p-6 rounded-3xl shadow-sm border border-slate-100">
                            <div class="flex items-center gap-2 mb-6">
                                <h4 class="font-black text-slate-800 uppercase tracking-widest text-sm italic">Creator
                                </h4>
                                <span class="text-[10px] text-slate-400">※敬称略</span>
                            </div>
                            <div class="space-y-4">
                                <div v-for="creator in creators" :key="creator.role" class="space-y-1">
                                    <p class="text-[10px] font-bold text-slate-400 uppercase">{{ creator.role }}</p>
                                    <p class="text-xs font-bold text-slate-700">{{ creator.name }}</p>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <section class="py-24 px-6 bg-slate-50 border-t border-slate-100">
            <div class="max-w-5xl mx-auto">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <a v-for="sns in socialLinks" :key="sns.name" :href="sns.url"
                        class="flex flex-col items-center p-8 bg-white rounded-3xl border border-slate-100 hover:border-blue-400 hover:shadow-2xl transition-all group">
                        <span class="text-4xl mb-4 group-hover:scale-110 transition-transform">{{ sns.icon }}</span>
                        <p class="font-black italic text-slate-900 text-lg uppercase">{{ sns.name }}</p>
                        <p class="text-blue-500 font-bold text-[10px] mt-1 tracking-widest">{{ sns.handle }}</p>
                    </a>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup lang="ts">
const profileTags = [
    { label: 'Fan Mark', value: '🐾💎' },
    { label: 'Fan Name', value: '汐猫観測隊' },
    { label: 'Stream Tag', value: '#汐猫LIVE' },
    { label: 'Art Tag', value: '#みおあーと' },
]

const pickupVideos = [
    {
        id: 1,
        title: '【自己紹介】1分でわかる汐猫みお',
        thumbnail: 'https://via.placeholder.com/640x360/2563eb/ffffff?text=Intro+Video',
        desc: '論理（VTuber）と物理（エンジニア）の二つの顔を持つ私の活動方針について。'
    },
    {
        id: 2,
        title: '【歌ってみた】Code:Meow',
        thumbnail: 'https://via.placeholder.com/640x360/1e293b/ffffff?text=Music+Video',
        desc: '中の人の専門分野である「コード」をテーマにしたオリジナルソングです。'
    },
]

const socialLinks = [
    { name: 'YouTube', handle: '@shioneko_mio', url: '#', icon: '📺' },
    { name: 'X / Twitter', handle: '@mio_shioneko', url: '#', icon: '🐦' },
    { name: 'Marshmallow', handle: 'Send Questions', url: '#', icon: '🍬' },
]


const fullProfile = [
  { label: '名前 / Name', value: '汐猫みお (しおね みお)' },
  { label: '職業 / Job', value: 'Virtual YouTuber / Programmer' },
  { label: '出身地 / Birthplace', value: '千葉県' },
  { label: '専門領域 / Domain', value: '情報科学全般（主に低レイヤー・セキュリティ・ソフトウェア）' },
  { label: '誕生日 / Birthday', value: '5月14日' },
  { label: '資格 / Cert', value: 'ITパスポート試験 / 情報セキュリティマネジメント試験' },
  { label: '言語 / Language', value: 'Japanese / English(Basic)' },
  { label: '生息地 / Habitat', value: 'インターネットの海' },
]

const techFavs = {
  os: ['Windows', 'Ubuntu', 'ChromeOS', 'Android'],
  languages: ['C', 'C++', 'Rust', 'Python', 'TypeScript']
}

const creators = [
  { role: 'キャラクターデザイン', name: '汐猫みお (@username)' },
  { role: 'Live2Dモデリング', name: '△△△△ (@username)' },
  { role: '背景・ロゴ制作', name: '□□□□ (@username)' },
]
</script>