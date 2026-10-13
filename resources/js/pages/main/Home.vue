<script setup lang="ts">
import { index } from '@/actions/App/Http/Controllers/Main/HomeController';
import MainFooter from '@/components/MainFooter.vue';
import MainHeader from '@/components/MainHeader.vue';
import Maintenance from '@/pages/main/Maintenance.vue';
import { PPOBBrandDataItem, PPOBCategoryDataItem } from '@/types/cms/ppob';
import { SliderDataItem } from '@/types/cms/web';
import { Head, Link, usePage } from '@inertiajs/vue3';
import { Shield, Zap, Lock, ChevronRight, Package } from 'lucide-vue-next';

defineProps<{
    sliders: SliderDataItem[];
    brands: any;
    featured_brands: PPOBBrandDataItem[];
    categories: PPOBCategoryDataItem[];
}>();

const page = usePage();
const setting = page.props.setting;

const steps = [
    {
        number: '1',
        icon: Package,
        title: 'Pilih Nominal',
        desc: 'Pilih paket Robux yang kamu inginkan dari daftar produk kami',
    },
    {
        number: '2',
        icon: Shield,
        title: 'Masukkan Username',
        desc: 'Ketik username Roblox kamu saja — tanpa password, tanpa login',
    },
    {
        number: '3',
        icon: Zap,
        title: 'Bayar & Selesai',
        desc: 'Bayar via QRIS atau transfer bank, Robux langsung masuk instan',
    },
];

const features = [
    {
        icon: Shield,
        title: 'Tanpa Login',
        desc: 'Cukup masukkan username Roblox kamu. Tidak perlu password atau data akun apapun.',
    },
    {
        icon: Zap,
        title: 'Proses Instan',
        desc: 'Robux masuk dalam hitungan detik setelah pembayaran dikonfirmasi.',
    },
    {
        icon: Lock,
        title: '100% Aman',
        desc: 'Privasi akun kamu sepenuhnya terjaga. Kami tidak menyimpan data sensitif.',
    },
];
</script>

<template>
    <Head>
        <title>{{ setting?.title || 'MarBlox.id' }} - Top Up Robux Instan Tanpa Login</title>
        <meta
            name="description"
            content="Top up Robux dengan mudah dan aman. Cukup masukkan username Roblox, pilih nominal, bayar, dan Robux langsung masuk. Tanpa login, tanpa ribet."
        />
        <component :is="'script'" type="application/ld+json">
            {{
                JSON.stringify({
                    '@context': 'https://schema.org',
                    '@type': 'WebSite',
                    name: setting?.title || 'MarBlox.id',
                    url: index().url,
                })
            }}
        </component>
    </Head>

    <div class="flex min-h-screen flex-col" style="background-color: #0a0a0a; color: #ffffff;">
        <!-- Header -->
        <MainHeader />

        <template v-if="setting?.maintenance_status === 'active'">
            <Maintenance />
        </template>

        <main v-else class="flex-1">

            <!-- ============ HERO SECTION ============ -->
            <section class="marblox-hero relative overflow-hidden py-20 md:py-32">
                <!-- Background grid pattern -->
                <div class="marblox-grid-bg absolute inset-0 pointer-events-none"></div>
                <!-- Red glow top center -->
                <div class="marblox-glow absolute inset-0 pointer-events-none"></div>

                <div class="relative mx-auto max-w-5xl px-4 text-center">
                    <!-- Badge -->
                    <div class="mb-6 inline-flex items-center gap-2 rounded-full border border-red-500/30 bg-red-500/10 px-4 py-1.5">
                        <span class="h-2 w-2 animate-pulse rounded-full bg-red-500"></span>
                        <span class="text-sm font-medium text-red-400">Platform Top Up Robux Terpercaya</span>
                    </div>

                    <!-- Headline -->
                    <h1 class="mb-4 text-4xl font-black leading-tight tracking-tight md:text-6xl lg:text-7xl">
                        Top Up Robux
                        <span class="marblox-gradient-text block">Instan & Aman</span>
                    </h1>

                    <!-- Subtitle -->
                    <p class="mx-auto mb-8 max-w-xl text-base text-gray-400 md:text-lg">
                        Cukup masukkan <strong class="text-white">username Roblox</strong> kamu,
                        pilih nominal, dan Robux langsung masuk. Tanpa login, tanpa ribet.
                    </p>

                    <!-- CTA Button -->
                    <div class="flex flex-col items-center gap-4 sm:flex-row sm:justify-center">
                        <a
                            href="#produk"
                            class="marblox-btn-primary inline-flex items-center gap-2 rounded-xl px-8 py-4 text-base font-bold transition-all"
                        >
                            Top Up Sekarang
                            <ChevronRight class="h-5 w-5" />
                        </a>
                        <Link
                            href="/cek-transaksi"
                            class="inline-flex items-center gap-2 rounded-xl border border-gray-700 bg-white/5 px-8 py-4 text-base font-semibold text-gray-300 transition-all hover:border-gray-500 hover:bg-white/10"
                        >
                            Cek Transaksi
                        </Link>
                    </div>

                    <!-- Trust Badges -->
                    <div class="mt-10 flex flex-wrap items-center justify-center gap-6 text-sm text-gray-500">
                        <div class="flex items-center gap-2">
                            <Shield class="h-4 w-4 text-red-500" />
                            <span>100% Aman</span>
                        </div>
                        <div class="w-px h-4 bg-gray-700 hidden sm:block"></div>
                        <div class="flex items-center gap-2">
                            <Zap class="h-4 w-4 text-red-500" />
                            <span>Proses Kedip</span>
                        </div>
                        <div class="w-px h-4 bg-gray-700 hidden sm:block"></div>
                        <div class="flex items-center gap-2">
                            <Lock class="h-4 w-4 text-red-500" />
                            <span>Tanpa Login</span>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ============ CARA ORDER SECTION ============ -->
            <section class="py-16 md:py-24" style="background-color: #0f0f0f;">
                <div class="mx-auto max-w-6xl px-4">
                    <!-- Section Header -->
                    <div class="mb-12 text-center">
                        <p class="mb-2 text-sm font-semibold uppercase tracking-widest text-red-500">Mudah & Cepat</p>
                        <h2 class="text-3xl font-black md:text-4xl">Cara Top Up Robux</h2>
                        <p class="mt-3 text-gray-400">Hanya 3 langkah mudah, Robux langsung masuk ke akun kamu</p>
                    </div>

                    <!-- Steps -->
                    <div class="relative grid gap-6 md:grid-cols-3">
                        <!-- Connector line (desktop only) -->
                        <div class="absolute left-1/2 top-10 hidden h-0.5 w-2/3 -translate-x-1/2 md:block"
                             style="background: linear-gradient(90deg, transparent, #EF4444, transparent);"></div>

                        <div
                            v-for="(step, i) in steps"
                            :key="i"
                            class="marblox-step-card relative flex flex-col items-center rounded-2xl p-8 text-center"
                        >
                            <!-- Number circle -->
                            <div class="marblox-step-number mb-5 flex h-12 w-12 items-center justify-center rounded-full text-xl font-black text-white">
                                {{ step.number }}
                            </div>
                            <!-- Icon -->
                            <div class="mb-4 flex h-14 w-14 items-center justify-center rounded-xl bg-red-500/10">
                                <component :is="step.icon" class="h-7 w-7 text-red-500" />
                            </div>
                            <h3 class="mb-2 text-lg font-bold text-white">{{ step.title }}</h3>
                            <p class="text-sm leading-relaxed text-gray-400">{{ step.desc }}</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ============ PRODUCTS SECTION ============ -->
            <section id="produk" class="py-16 md:py-24" style="background-color: #0a0a0a;">
                <div class="mx-auto max-w-7xl px-4">
                    <!-- Section Header -->
                    <div class="mb-10 text-center">
                        <p class="mb-2 text-sm font-semibold uppercase tracking-widest text-red-500">Pilihan Lengkap</p>
                        <h2 class="text-3xl font-black md:text-4xl">Pilih Paket Robux</h2>
                        <p class="mt-3 text-gray-400">Tersedia berbagai nominal sesuai kebutuhan kamu</p>
                    </div>

                    <!-- Category Filter -->
                    <div v-if="categories && categories.length > 0" class="mb-8 flex flex-wrap gap-3 justify-center">
                        <Link
                            :href="index().url"
                            class="marblox-tag inline-flex items-center gap-2 rounded-full border border-red-500 bg-red-500/10 px-4 py-2 text-sm font-semibold text-red-400"
                        >
                            Semua
                        </Link>
                        <Link
                            v-for="category in categories"
                            :href="index().url + '?category=' + category.slug"
                            :key="category.id"
                            class="marblox-tag inline-flex items-center gap-2 rounded-full border border-gray-700 px-4 py-2 text-sm font-semibold text-gray-400 transition-all hover:border-red-500/50 hover:text-red-400"
                        >
                            {{ category.name }}
                        </Link>
                    </div>

                    <!-- Featured Brands Grid -->
                    <div
                        v-if="featured_brands && featured_brands.length > 0"
                        class="grid gap-4 grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6"
                    >
                        <Link
                            v-for="brand in featured_brands"
                            :key="brand.id"
                            :href="`/topup/${brand.slug}`"
                            class="marblox-brand-card group relative flex flex-col items-center rounded-2xl p-5 text-center transition-all"
                        >
                            <!-- Popular badge -->
                            <span
                                v-if="brand.is_featured"
                                class="absolute -top-2 left-1/2 -translate-x-1/2 rounded-full bg-red-500 px-3 py-0.5 text-xs font-bold text-white whitespace-nowrap"
                            >
                                TERPOPULER
                            </span>

                            <!-- Brand Image -->
                            <div class="mb-3 flex h-16 w-16 items-center justify-center overflow-hidden rounded-xl bg-white/5">
                                <img
                                    v-if="brand.image"
                                    :src="brand.image"
                                    :alt="brand.name"
                                    class="h-full w-full object-contain p-1"
                                />
                                <span v-else class="text-3xl">🎮</span>
                            </div>

                            <h3 class="text-sm font-bold text-white leading-tight">{{ brand.name }}</h3>
                            <p class="mt-1 text-xs text-gray-500">
                                {{ brand.active_products_count ?? 0 }} produk
                            </p>

                            <!-- Hover arrow -->
                            <div class="mt-3 flex items-center gap-1 text-xs font-semibold text-red-500 opacity-0 transition-opacity group-hover:opacity-100">
                                Top Up <ChevronRight class="h-3 w-3" />
                            </div>
                        </Link>
                    </div>

                    <!-- All Brands -->
                    <div v-if="brands?.data && brands.data.length > 0" class="mt-6">
                        <div class="mb-6 flex items-center gap-3">
                            <h3 class="text-lg font-bold text-white">Semua Produk</h3>
                            <div class="h-px flex-1 bg-gray-800"></div>
                        </div>
                        <div class="grid gap-4 grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6">
                            <Link
                                v-for="brand in brands.data"
                                :key="brand.id"
                                :href="`/topup/${brand.slug}`"
                                class="marblox-brand-card group flex flex-col items-center rounded-2xl p-5 text-center transition-all"
                            >
                                <div class="mb-3 flex h-16 w-16 items-center justify-center overflow-hidden rounded-xl bg-white/5">
                                    <img
                                        v-if="brand.image"
                                        :src="brand.image"
                                        :alt="brand.name"
                                        class="h-full w-full object-contain p-1"
                                    />
                                    <span v-else class="text-3xl">🎮</span>
                                </div>
                                <h3 class="text-sm font-bold text-white leading-tight">{{ brand.name }}</h3>
                                <p class="mt-1 text-xs text-gray-500">{{ brand.active_products_count ?? 0 }} produk</p>
                                <div class="mt-3 flex items-center gap-1 text-xs font-semibold text-red-500 opacity-0 transition-opacity group-hover:opacity-100">
                                    Top Up <ChevronRight class="h-3 w-3" />
                                </div>
                            </Link>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ============ FEATURES SECTION ============ -->
            <section class="py-16 md:py-24" style="background-color: #0f0f0f;">
                <div class="mx-auto max-w-5xl px-4">
                    <div class="mb-12 text-center">
                        <p class="mb-2 text-sm font-semibold uppercase tracking-widest text-red-500">Kenapa MarBlox.id?</p>
                        <h2 class="text-3xl font-black md:text-4xl">Keunggulan Kami</h2>
                    </div>

                    <div class="grid gap-6 md:grid-cols-3">
                        <div
                            v-for="(feature, i) in features"
                            :key="i"
                            class="marblox-feature-card rounded-2xl p-8"
                        >
                            <div class="mb-5 flex h-14 w-14 items-center justify-center rounded-xl bg-red-500/10">
                                <component :is="feature.icon" class="h-7 w-7 text-red-500" />
                            </div>
                            <h3 class="mb-3 text-xl font-bold text-white">{{ feature.title }}</h3>
                            <p class="text-sm leading-relaxed text-gray-400">{{ feature.desc }}</p>
                        </div>
                    </div>
                </div>
            </section>

        </main>

        <!-- Footer -->
        <MainFooter />
    </div>
</template>

<style scoped>
/* Hero background */
.marblox-hero {
    background-color: #0a0a0a;
}

.marblox-grid-bg {
    background-image:
        linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
    background-size: 40px 40px;
}

.marblox-glow {
    background: radial-gradient(ellipse 60% 40% at 50% 0%, rgba(239, 68, 68, 0.12) 0%, transparent 70%);
}

/* Gradient text */
.marblox-gradient-text {
    background: linear-gradient(135deg, #FF3333, #FF6B6B);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

/* Primary button */
.marblox-btn-primary {
    background: linear-gradient(135deg, #EF4444, #DC2626);
    color: #ffffff;
    box-shadow: 0 0 20px rgba(239, 68, 68, 0.3);
}
.marblox-btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 30px rgba(239, 68, 68, 0.5);
}

/* Step cards */
.marblox-step-card {
    background-color: #141414;
    border: 1px solid #222222;
    transition: border-color 0.3s, transform 0.3s;
}
.marblox-step-card:hover {
    border-color: rgba(239, 68, 68, 0.4);
    transform: translateY(-4px);
}

.marblox-step-number {
    background: linear-gradient(135deg, #EF4444, #DC2626);
    box-shadow: 0 0 16px rgba(239, 68, 68, 0.4);
}

/* Brand cards */
.marblox-brand-card {
    background-color: #141414;
    border: 1px solid #1f1f1f;
    cursor: pointer;
}
.marblox-brand-card:hover {
    border-color: rgba(239, 68, 68, 0.4);
    background-color: #1a1a1a;
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(239, 68, 68, 0.1);
}

/* Feature cards */
.marblox-feature-card {
    background-color: #141414;
    border: 1px solid #1f1f1f;
    transition: border-color 0.3s, transform 0.3s;
}
.marblox-feature-card:hover {
    border-color: rgba(239, 68, 68, 0.3);
    transform: translateY(-4px);
}
</style>
