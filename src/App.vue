<script setup lang="ts">
import { ref } from 'vue'

const activeMenu = ref(false)

const menuItems = [
  {
    title: 'قهوه‌های گرم',
    description: 'عطر دلنشین قهوه، برای لحظه‌های خاص',
    image:
      'https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=700&q=85',
    items: ['اسپرسو', 'آمریکانو', 'کاپوچینو', 'لاته'],
  },
  {
    title: 'چای و دمنوش',
    description: 'یک فنجان آرامش در روزهای شلوغ',
    image:
      'https://images.unsplash.com/photo-1544787219-7f47ccb76574?auto=format&fit=crop&w=700&q=85',
    items: ['چای ایرانی', 'چای ماسالا', 'دمنوش آرامش', 'چای سبز'],
  },
  {
    title: 'آیس کافی و شیک',
    description: 'خنک، تازه و دوست‌داشتنی',
    image:
      'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?auto=format&fit=crop&w=700&q=85',
    items: ['آیس لاته', 'آیس آمریکانو', 'شیک شکلات', 'فراپه'],
  },
  {
    title: 'صبحانه و میان‌وعده',
    description: 'طعم خوشمزه برای شروع یک روز خوب',
    image:
      'https://images.unsplash.com/photo-1533089860892-a7c6f0a88666?auto=format&fit=crop&w=700&q=85',
    items: ['صبحانه انگلیسی', 'پنکیک', 'کیک روز', 'کروسان'],
  },
]

const galleryImages = [
  'photo-1442512595331-e89e73853f31',
  'photo-1495474472287-4d71bcdd2085',
  'photo-1501339847302-ac426a4a7cbb',
  'photo-1511920170033-f8396924c348',
  'photo-1461023058943-07fcbe16d735',
]

const navItems = [
  { label: 'خانه', href: '#home' },
  { label: 'منوی کافه', href: '#menu' },
  { label: 'درباره ما', href: '#about' },
  { label: 'گالری', href: '#gallery' },
  { label: 'تماس با ما', href: '#contact' },
]
</script>

<template>
  <main dir="rtl" class="min-h-screen overflow-hidden bg-[#FAF8F2] text-[#243D2D]">
    <!-- Header -->
    <header dir="rtl" class="relative z-50 px-3 pt-4 sm:px-6 lg:px-10 lg:pt-6">
      <div
        class="relative mx-auto flex max-w-[1600px] items-center justify-between gap-3 rounded-[24px] border border-[#E7DDC8] bg-[#FCF8ED]/95 px-4 py-3 shadow-[0_10px_35px_rgba(55,64,42,0.07)] backdrop-blur-md sm:px-6 sm:py-4 lg:gap-6 lg:px-8"
      >
        <!-- تزئین گیاهی گوشه هدر -->
        <div
          aria-hidden="true"
          class="pointer-events-none absolute -left-2 -top-2 hidden h-16 w-16 rounded-full bg-[#DCE1CD]/30 blur-2xl sm:block"
        ></div>

        <!-- لوگو -->
        <a href="#home" class="group relative flex shrink-0 items-center gap-3">
          <span
            class="flex h-12 w-12 items-center justify-center rounded-full border border-[#D7CBAE] bg-[#173D30] text-[#F8F0DB] shadow-[0_4px_12px_rgba(23,61,48,0.15)] transition duration-300 group-hover:rotate-[-6deg] group-hover:scale-105 sm:h-14 sm:w-14"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 64 64"
              fill="none"
              stroke="currentColor"
              stroke-width="2.6"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="h-8 w-8 sm:h-9 sm:w-9"
              aria-hidden="true"
            >
              <path d="M15 28h31v13a12 12 0 0 1-12 12h-7a12 12 0 0 1-12-12V28Z" />
              <path d="M46 32h4a7 7 0 0 1 0 14h-7" />
              <path d="M24 21c-4-5 5-6 1-12M33 21c-4-5 5-6 1-12M41 23c-3-4 3-5 1-9" />
              <path d="M11 57h40" />
            </svg>
          </span>

          <span class="whitespace-nowrap">
            <span
              class="block text-xl font-black tracking-tight text-[#173D30] sm:text-2xl lg:text-[27px]"
            >
              کافه چی
            </span>
            <span
              dir="ltr"
              class="mt-1 block text-[9px] font-medium tracking-[0.42em] text-[#B18451] sm:text-[10px]"
            >
              CAFE CHI
            </span>
          </span>
        </a>

        <!-- منوی دسکتاپ -->
        <nav aria-label="منوی اصلی" class="hidden items-center gap-5 xl:gap-8 lg:flex">
          <a
            v-for="item in navItems"
            :key="item.href"
            :href="item.href"
            class="group relative whitespace-nowrap py-3 text-sm font-medium text-[#45574A] transition-colors duration-300 hover:text-[#B18451] xl:text-[15px]"
          >
            {{ item.label }}
            <span
              class="absolute bottom-1 right-0 h-[2px] w-0 rounded-full bg-[#B18451] transition-all duration-300 group-hover:w-full"
            ></span>
          </a>
        </nav>

        <!-- دکمه‌های سمت چپ -->
        <div class="flex shrink-0 items-center gap-2 sm:gap-3">
          <a
            href="#contact"
            class="hidden items-center justify-center gap-2 bg-[#A77943] rounded-full px-5 py-3 text-sm font-bold text-white shadow-[0_5px_15px_rgba(23,61,48,0.13)] transition duration-300 hover:-translate-y-0.5 sm:inline-flex lg:px-6"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              class="h-5 w-5"
              aria-hidden="true"
            >
              <rect x="3" y="5" width="18" height="16" rx="3" />
              <path
                d="M16 3v4M8 3v4M3 10h18M9 15l2 2 4-4"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
            رزرو میز
          </a>

          <!-- دکمه منوی موبایل -->
          <button
            type="button"
            class="flex h-11 w-11 items-center justify-center rounded-xl border border-[#E5DCC8] bg-[#FCF8ED] text-[#173D30] transition hover:border-[#B18451] hover:bg-[#F4EBDD] lg:hidden"
            :aria-expanded="activeMenu"
            aria-controls="mobile-navigation"
            :aria-label="activeMenu ? 'بستن منو' : 'باز کردن منو'"
            @click="activeMenu = !activeMenu"
          >
            <svg
              v-if="!activeMenu"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              stroke-linecap="round"
              class="h-6 w-6"
              aria-hidden="true"
            >
              <path d="M4 6h16M4 12h16M4 18h16" />
            </svg>

            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              stroke-linecap="round"
              class="h-6 w-6"
              aria-hidden="true"
            >
              <path d="m6 6 12 12M18 6 6 18" />
            </svg>
          </button>
        </div>
      </div>

      <!-- منوی کشویی موبایل -->
      <Transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="translate-y-2 opacity-0"
        enter-to-class="translate-y-0 opacity-100"
        leave-active-class="transition duration-150 ease-in"
        leave-from-class="translate-y-0 opacity-100"
        leave-to-class="translate-y-2 opacity-0"
      >
        <nav
          v-if="activeMenu"
          id="mobile-navigation"
          aria-label="منوی موبایل"
          class="absolute left-3 right-3 top-full mx-auto mt-2 max-w-[1600px] rounded-[22px] border border-[#E7DDC8] bg-[#FCF8ED] p-3 shadow-[0_18px_45px_rgba(37,52,36,0.13)] sm:left-6 sm:right-6 lg:hidden"
        >
          <a
            v-for="(item, index) in navItems"
            :key="item.href"
            :href="item.href"
            class="flex items-center justify-between rounded-xl px-4 py-3.5 text-sm text-[#294638] transition duration-200 hover:bg-[#F1EBDD] hover:text-[#A87943]"
            :class="index !== navItems.length - 1 ? 'border-b border-[#E9E0CE]' : ''"
            @click="activeMenu = false"
          >
            <span>{{ item.label }}</span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.7"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="h-5 w-5"
              aria-hidden="true"
            >
              <path d="m9 18 6-6-6-6" />
            </svg>
          </a>

          <a
            href="#contact"
            class="mt-3 flex items-center justify-center gap-2 rounded-full bg-[#A77943] px-5 py-3.5 text-sm font-bold text-white transition hover:bg-[#285442]"
            @click="activeMenu = false"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              class="h-5 w-5"
              aria-hidden="true"
            >
              <rect x="3" y="5" width="18" height="16" rx="3" />
              <path d="M16 3v4M8 3v4M3 10h18" />
            </svg>
            رزرو میز
          </a>
        </nav>
      </Transition>
    </header>

    <!-- Hero -->
    <section id="home" class="px-4 pb-16 pt-10 sm:px-8 sm:pt-16 lg:px-14 lg:pb-24 lg:pt-20">
      <div class="mx-auto grid max-w-[1400px] items-center gap-12 lg:grid-cols-2 lg:gap-16">
        <div class="order-2 lg:order-1">
          <span
            class="inline-flex items-center gap-2 rounded-full border border-[#E6DDC8] bg-[#F3EFE2] px-4 py-2 text-xs font-semibold text-[#6E795E] sm:text-sm"
          >
            <span class="h-2 w-2 rounded-full bg-[#B68A52]"></span>
            یه فنجون حال خوب، همین نزدیکی
          </span>

          <h1
            class="mt-7 text-4xl leading-[1.65] font-black tracking-tight sm:text-5xl lg:text-[64px] lg:leading-[1.5]"
          >
            قهوه‌مون
            <span class="relative inline-block text-[#A77943]"> یادمونه... </span>
            <br />
            <span class="text-[#294431]">حالت خوب می‌شه!</span>
          </h1>

          <p class="mt-6 max-w-xl text-sm leading-8 text-[#73776B] sm:text-base sm:leading-9">
            اینجا کافه چیه؛ جایی برای عطر قهوه تازه، گفت‌وگوهای دلچسب و لحظه‌هایی که دوست داری
            طولانی‌تر بشن. یه گوشه دنج برای خودت پیدا کن.
          </p>

          <div class="mt-8 flex flex-wrap gap-3 sm:gap-4">
            <a
              href="#menu"
              class="inline-flex items-center justify-center gap-3 rounded-xl px-6 py-4 text-sm font-bold text-white transition hover:-translate-y-0.5 bg-[#A77943] sm:px-8"
            >
              منوی کافه
              <span aria-hidden="true">←</span>
            </a>
            <a
              href="#about"
              class="inline-flex items-center justify-center rounded-xl border border-[#DCDCCF] bg-[#FFFDF8] px-6 py-4 text-sm font-bold transition hover:border-[#294431] sm:px-8"
            >
              داستان ما
            </a>
          </div>
        </div>

        <div class="relative order-1 mx-auto w-full max-w-[650px] lg:order-2 lg:mr-auto">
          <div class="absolute -inset-3 -rotate-2 rounded-[34px] bg-[#E9E2D0] sm:-inset-5"></div>
          <div class="relative overflow-hidden rounded-[28px] bg-[#E7E0D1]">
            <img
              src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?auto=format&fit=crop&w=1200&q=90"
              alt="قهوه تازه و فضای گرم کافه"
              fetchpriority="high"
              class="h-[350px] w-full object-cover sm:h-[480px] lg:h-[570px]"
            />
            <div
              class="absolute inset-x-4 bottom-4 flex items-center justify-between rounded-2xl border border-white/30 bg-[#FFFDF3]/95 p-4 shadow-lg backdrop-blur-md sm:inset-x-6 sm:bottom-6 sm:p-5"
            >
              <div>
                <p class="text-sm font-black sm:text-base">یه مکث کوچیک برای خودت</p>
                <p class="mt-2 text-xs text-[#77796D]">عطر قهوه، طعم زندگی</p>
              </div>
              <span
                class="flex h-12 w-12 items-center justify-center rounded-xl bg-[#E9E6D8] text-2xl"
              >
                ♨
              </span>
            </div>
          </div>
          <div
            class="absolute -right-2 top-8 rounded-2xl border border-[#E8E1D2] bg-[#FFFDF8] px-4 py-3 shadow-lg sm:-right-7 sm:top-12 sm:px-5 sm:py-4"
          >
            <span class="block text-lg font-black">تازه و خوش‌عطر</span>
            <span class="mt-1 block text-xs text-[#8A897A]">از اولین جرعه لذت ببر</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Menu -->
    <section id="menu" class="bg-[#F0EEE4] px-4 py-16 sm:px-8 sm:py-20 lg:px-14 lg:py-24">
      <div class="mx-auto max-w-[1400px]">
        <div class="flex flex-col justify-between gap-5 sm:flex-row sm:items-end">
          <div>
            <span class="text-xs font-bold tracking-widest text-[#A77943]">TASTE OUR MENU</span>
            <h2 class="mt-3 text-3xl font-black sm:text-4xl">یه چیزی برای هر سلیقه</h2>
            <p class="mt-4 text-sm leading-7 text-[#77796D]">
              از قهوه‌های کلاسیک تا طعم‌های جدید و هیجان‌انگیز.
            </p>
          </div>
          <a
            href="#contact"
            class="inline-flex w-fit items-center gap-3 rounded-xl border border-[#DADBCD] bg-[#FAF8F2] px-5 py-3 text-sm font-bold transition hover:border-[#294431]"
          >
            سفارش و اطلاعات بیشتر
            <span aria-hidden="true">←</span>
          </a>
        </div>

        <div class="mt-10 grid gap-5 sm:grid-cols-2 xl:grid-cols-4">
          <article
            v-for="(item, index) in menuItems"
            :key="item.title"
            class="group overflow-hidden rounded-2xl border border-[#E3E0D4] bg-[#FFFDF8] transition duration-300 hover:-translate-y-1 hover:shadow-xl"
          >
            <div class="relative overflow-hidden">
              <img
                :src="item.image"
                :alt="item.title"
                loading="lazy"
                class="h-52 w-full object-cover transition duration-500 group-hover:scale-105"
              />
            </div>

            <div class="p-5 sm:p-6">
              <h3 class="text-xl font-black">{{ item.title }}</h3>
              <p class="mt-2 text-xs leading-6 text-[#858779]">{{ item.description }}</p>

              <ul class="mt-5 space-y-3 border-t border-[#ECE9DE] pt-4">
                <li
                  v-for="drink in item.items"
                  :key="drink"
                  class="flex items-center gap-2 text-sm text-[#555F50]"
                >
                  <span class="h-1.5 w-1.5 rounded-full bg-[#B68A52]"></span>
                  {{ drink }}
                </li>
              </ul>

              <a
                href="#contact"
                class="mt-6 flex items-center justify-between border-t border-[#ECE9DE] pt-4 text-sm font-bold text-[#294431]"
              >
                اطلاعات سفارش
                <span aria-hidden="true">←</span>
              </a>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- About -->
    <section id="about" class="px-4 py-16 sm:px-8 sm:py-20 lg:px-14 lg:py-24">
      <div class="mx-auto grid max-w-[1400px] items-center gap-10 lg:grid-cols-2 lg:gap-16">
        <div class="relative">
          <img
            src="https://images.unsplash.com/photo-1445116572660-236099ec97a0?auto=format&fit=crop&w=1200&q=85"
            alt="فضای گرم و دلنشین کافه"
            loading="lazy"
            class="h-[330px] w-full rounded-[28px] object-cover sm:h-[450px]"
          />
          <div
            class="absolute -bottom-5 left-4 rounded-2xl bg-[#294431] px-6 py-5 text-white shadow-xl sm:left-8 sm:px-8"
          >
            <p class="text-2xl font-black">کافه چی</p>
            <p class="mt-2 text-xs text-white/70">برای لحظه‌های دوست‌داشتنی</p>
          </div>
        </div>

        <div class="pt-4 lg:pt-0">
          <span class="text-xs font-bold tracking-widest text-[#A77943]">OUR STORY</span>
          <h2 class="mt-4 text-3xl leading-relaxed font-black sm:text-4xl">
            ما به قهوه فقط
            <br />
            <span class="text-[#A77943]">به چشم یه نوشیدنی</span>
            نگاه نمی‌کنیم.
          </h2>
          <p class="mt-6 text-sm leading-9 text-[#74776A]">
            برای ما کافه جاییه که روزهای شلوغ کمی آروم‌تر می‌شن؛ جایی برای دیدن دوست‌ها، شروع یک
            ایده تازه یا حتی چند دقیقه خلوت با خودت. در کافه چی تلاش می‌کنیم هر فنجون، بخشی از یک
            تجربه دوست‌داشتنی باشه.
          </p>
          <p class="mt-4 text-sm leading-9 text-[#74776A]">
            از انتخاب دانه‌های قهوه تا آماده کردن سفارش، به کیفیت و جزئیات اهمیت می‌دیم؛ چون فکر
            می‌کنیم حال خوب از همین چیزهای کوچیک شروع می‌شه.
          </p>
          <a
            href="#contact"
            class="mt-7 inline-flex items-center gap-3 rounded-xl bg-[#A77943] px-7 py-4 text-sm font-bold text-white transition"
          >
            بیشتر با ما آشنا شو
            <span aria-hidden="true">←</span>
          </a>
        </div>
      </div>
    </section>

    <!-- Gallery -->
    <section id="gallery" class="bg-[#F0EEE4] px-4 py-16 sm:px-8 sm:py-20 lg:px-14 lg:py-24">
      <div class="mx-auto max-w-[1400px]">
        <div class="text-center">
          <span class="text-xs font-bold tracking-widest text-[#A77943]">A LOOK INSIDE</span>
          <h2 class="mt-3 text-3xl font-black sm:text-4xl">چند قاب از حال خوب ما</h2>
          <p class="mt-4 text-sm leading-7 text-[#77796D]">
            عطر قهوه، میزهای دنج و لحظه‌هایی که ارزش ثبت کردن دارن.
          </p>
        </div>

        <div class="mt-10 grid grid-cols-2 gap-3 sm:grid-cols-3 sm:gap-5 lg:grid-cols-5">
          <div
            v-for="(image, index) in galleryImages"
            :key="image"
            class="group overflow-hidden rounded-2xl bg-[#E2DDCF]"
            :class="index === 1 || index === 3 ? 'sm:translate-y-6' : ''"
          >
            <img
              :src="`https://images.unsplash.com/${image}?auto=format&fit=crop&w=600&q=80`"
              :alt="`تصویر شماره ${index + 1} از کافه چی`"
              loading="lazy"
              class="h-48 w-full object-cover transition duration-500 group-hover:scale-110 sm:h-64 lg:h-72"
            />
          </div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact" dir="rtl" class="bg-[#FAF7ED] px-4 py-8 sm:px-8 lg:px-10">
      <div class="mx-auto max-w-[1400px]">
        <!-- Section title -->
        <div class="mb-5 flex items-center justify-center gap-4">
          <span class="h-px w-12 bg-[#8B9A83]"></span>

          <h2 class="whitespace-nowrap text-lg font-black text-[#174536]">تماس با ما</h2>

          <span class="h-px w-12 bg-[#8B9A83]"></span>
        </div>

        <!-- Contact cards -->
        <div class="grid grid-cols-1 gap-3 sm:grid-cols-2 lg:grid-cols-4">
          <!-- Phone -->
          <a
            href="tel:09303236974"
            class="flex min-h-[82px] items-center gap-3 rounded-xl border border-[#E4DDCB] bg-[#FBF8EF] px-4 py-3 transition-colors hover:border-[#174536]"
          >
            <span
              class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-[#104C3D] text-white"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="h-6 w-6"
                aria-hidden="true"
              >
                <path
                  d="M6.62 10.79a15.05 15.05 0 006.59 6.59l2.2-2.2a1 1 0 011.01-.24c1.12.37 2.33.56 3.58.56a1 1 0 011 1V20a1 1 0 01-1 1C10.61 21 3 13.39 3 4a1 1 0 011-1h3.5a1 1 0 011 1c0 1.25.19 2.46.56 3.58a1 1 0 01-.25 1.01l-2.19 2.2z"
                />
              </svg>
            </span>

            <span class="min-w-0">
              <span class="block text-xs font-bold text-[#264536]"> تلفن </span>
              <span
                dir="ltr"
                class="mt-1 block whitespace-nowrap text-sm font-black text-[#183D2F] sm:text-base"
              >
                0930 32 36 974
              </span>
            </span>
          </a>

          <!-- Instagram -->
          <a
            href="https://instagram.com/Cafechii__"
            target="_blank"
            rel="noopener noreferrer"
            class="flex min-h-[82px] items-center gap-3 rounded-xl border border-[#E4DDCB] bg-[#FBF8EF] px-4 py-3 transition-colors hover:border-[#174536]"
          >
            <span
              class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-[#104C3D] text-white"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
                class="h-6 w-6"
                aria-hidden="true"
              >
                <rect x="3" y="3" width="18" height="18" rx="5" />
                <circle cx="12" cy="12" r="4" />
                <circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none" />
              </svg>
            </span>

            <span class="min-w-0">
              <span class="block text-xs font-bold text-[#264536]"> اینستاگرام </span>
              <span dir="ltr" class="mt-1 block text-sm font-black text-[#183D2F] sm:text-base">
                @Cafechii__
              </span>
            </span>
          </a>

          <!-- Address -->
          <a
            href="https://neshan.org/maps/places/2f1a8f2af8e44e94923646c23bcc4c5e#c35.713-51.362-20z-0p"
            target="_blank"
            rel="noopener noreferrer"
            class="flex min-h-[82px] items-center gap-3 rounded-xl border border-[#E4DDCB] bg-[#FBF8EF] px-4 py-3 transition-colors hover:border-[#174536]"
          >
            <span
              class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-[#104C3D] text-white"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="h-6 w-6"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M12 2a7 7 0 00-7 7c0 5.25 7 13 7 13s7-7.75 7-13a7 7 0 00-7-7zm0 10a3 3 0 110-6 3 3 0 010 6z"
                  clip-rule="evenodd"
                />
              </svg>
            </span>

            <span class="min-w-0">
              <span class="block text-xs font-bold text-[#264536]"> آدرس کافه </span>
              <span class="mt-1 block text-xs leading-5 text-[#62685A] sm:text-sm">
                روی نقشه ببینید
              </span>
            </span>
          </a>

          <!-- Working hours -->
          <div
            class="flex min-h-[82px] items-center gap-3 rounded-xl border border-[#E4DDCB] bg-[#FBF8EF] px-4 py-3"
          >
            <span
              class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-[#104C3D] text-white"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.7"
                class="h-6 w-6"
                aria-hidden="true"
              >
                <circle cx="12" cy="12" r="9" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 7v5l3 2" />
              </svg>
            </span>

            <span class="min-w-0">
              <span class="block text-xs font-bold text-[#264536]"> ساعات کاری </span>
              <span class="mt-1 block text-sm font-black text-[#183D2F]"> همه روزه </span>
              <span class="mt-1 block text-xs text-[#62685A]"> منتظر شما هستیم </span>
            </span>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer dir="rtl" class="px-3 pb-4 pt-6 sm:px-6 lg:px-10">
      <div
        class="relative mx-auto max-w-[1600px] overflow-hidden rounded-[24px] border border-[#496858] bg-[#0D3328] text-[#F8F2DF] shadow-[0_16px_45px_rgba(24,49,35,0.12)]"
      >
        <div
          aria-hidden="true"
          class="pointer-events-none absolute -left-10 -top-10 h-48 w-48 rounded-full bg-[#C4A76A]/[0.06] blur-3xl"
        ></div>

        <div
          class="relative grid gap-8 px-6 py-8 sm:px-9 sm:py-10 lg:grid-cols-[1fr_1.6fr_1fr] lg:items-center lg:gap-8 lg:px-12"
        >
          <a href="#home" class="group flex flex-col items-start">
            <div class="flex items-center gap-4">
              <span
                class="flex h-[76px] w-[76px] shrink-0 items-center justify-center rounded-full border border-[#A7B49A]/40 bg-[#F4EEDB]/[0.06] text-[#F4EEDB] transition duration-300 group-hover:border-[#D6BC83]"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 64 64"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2.5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="h-12 w-12"
                  aria-hidden="true"
                >
                  <path d="M17 27h29v14a12 12 0 0 1-12 12h-5a12 12 0 0 1-12-12V27Z" />
                  <path d="M46 31h4a7 7 0 0 1 0 14h-7" />
                  <path d="M24 20c-4-5 5-6 1-12M33 20c-4-5 5-6 1-12M42 22c-3-4 3-5 1-9" />
                  <path d="M13 57h39" />
                  <path d="M25 35c3 4 8 4 12 0" />
                </svg>
              </span>

              <span>
                <span class="block text-4xl font-black tracking-tight sm:text-5xl"> کافه چی </span>
                <span
                  dir="ltr"
                  class="mt-2 block text-xs font-medium tracking-[0.65em] text-[#D8BD80]"
                >
                  CAFE CHI
                </span>
              </span>
            </div>

            <p class="mt-5 text-sm leading-8 text-[#F1EBDC]/85 sm:text-base">
              جایی برای لحظه‌های خوب،
              <br />
              با طعم قهوه و آرامش...
            </p>
          </a>

          <nav
            aria-label="ناوبری فوتر"
            class="flex flex-wrap items-center justify-start gap-x-6 gap-y-5 border-y border-[#B7C0A9]/20 py-6 text-sm sm:gap-x-8 lg:justify-center lg:border-x lg:border-y-0 lg:px-6 lg:py-10"
          >
            <a
              v-for="item in navItems"
              :key="item.href"
              :href="item.href"
              class="group relative whitespace-nowrap text-[#F1EBDC]/80 transition-colors duration-200 hover:text-[#E5CD91]"
            >
              {{
                item.label === 'خانه'
                  ? 'خانه'
                  : item.label === 'منوی کافه'
                    ? 'منوی کافه'
                    : item.label === 'درباره ما'
                      ? 'درباره ما'
                      : item.label === 'گالری'
                        ? 'گالری'
                        : 'تماس با ما'
              }}
              <span
                class="absolute -bottom-3 right-0 h-0.5 w-0 bg-[#D9BE81] transition-all duration-300 group-hover:w-full"
              ></span>
            </a>
          </nav>

          <div class="flex flex-col items-start lg:items-center">
            <h3 class="text-base font-bold">ما را دنبال کنید</h3>

            <div class="mt-5 flex items-center gap-3">
              <a
                href="https://instagram.com/Cafechii__"
                target="_blank"
                rel="noopener noreferrer"
                aria-label="اینستاگرام کافه چی"
                class="flex h-12 w-12 items-center justify-center rounded-full border border-white/10 bg-white/[0.07] transition duration-300 hover:-translate-y-1 hover:bg-[#D6BC83] hover:text-[#15372B]"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.8"
                  class="h-6 w-6"
                  aria-hidden="true"
                >
                  <rect x="3" y="3" width="18" height="18" rx="5" />
                  <circle cx="12" cy="12" r="4" />
                  <circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none" />
                </svg>
              </a>

              <a
                href="https://t.me/"
                target="_blank"
                rel="noopener noreferrer"
                aria-label="تلگرام"
                class="flex h-12 w-12 items-center justify-center rounded-full border border-white/10 bg-white/[0.07] transition duration-300 hover:-translate-y-1 hover:bg-[#D6BC83] hover:text-[#15372B]"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                  class="h-6 w-6"
                  aria-hidden="true"
                >
                  <path
                    d="M21.8 3.2a1 1 0 0 0-1.04-.15L2.4 10.3a1.5 1.5 0 0 0 .13 2.82l4.6 1.56 1.72 5.14a1.5 1.5 0 0 0 2.66.36l2.6-3.43 4.3 3.16a1.5 1.5 0 0 0 2.36-.91l2.1-14.5a1.5 1.5 0 0 0-1.07-1.3ZM9 14.25l8.94-7.12-6.98 8.66-.35 2.56L9 14.25Z"
                  />
                </svg>
              </a>

              <a
                href="#contact"
                aria-label="راه‌های ارتباط با کافه"
                class="flex h-12 w-12 items-center justify-center rounded-full border border-white/10 bg-white/[0.07] transition duration-300 hover:-translate-y-1 hover:bg-[#D6BC83] hover:text-[#15372B]"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.8"
                  class="h-6 w-6"
                  aria-hidden="true"
                >
                  <rect x="3" y="3" width="18" height="18" rx="4" />
                  <circle cx="8" cy="8" r="2" />
                  <circle cx="16" cy="8" r="2" />
                  <path d="M5 17c0-3 2-5 4-5s4 2 4 5M13 17c0-3 2-5 4-5" />
                </svg>
              </a>
            </div>

            <p class="mt-5 text-sm italic text-[#D9BE81]">کافه چی، همیشه با شما ♡</p>
            <span class="mt-2 h-px w-24 rotate-[-5deg] bg-[#D9BE81]"></span>
          </div>
        </div>

        <div class="mx-6 h-px bg-[#B7C0A9]/25 sm:mx-9 lg:mx-12"></div>

        <div class="grid gap-3 px-6 py-6 sm:grid-cols-2 sm:px-9 lg:grid-cols-4 lg:px-12">
          <a
            href="tel:09303236974"
            class="group flex min-h-[100px] items-center gap-4 rounded-xl border border-[#A8B6A3]/40 bg-white/[0.025] px-4 py-4 transition duration-300 hover:border-[#D9BE81]/70 hover:bg-white/[0.05]"
          >
            <span
              class="flex h-14 w-14 shrink-0 items-center justify-center rounded-full bg-[#F4EEDB] text-[#173C2E] transition group-hover:bg-[#D9BE81]"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="h-7 w-7"
                aria-hidden="true"
              >
                <path
                  d="M6.62 10.79a15.05 15.05 0 0 0 6.59 6.59l2.2-2.2a1 1 0 0 1 1.01-.24c1.12.37 2.33.56 3.58.56a1 1 0 0 1 1 1V20a1 1 0 0 1-1 1C10.61 21 3 13.39 3 4a1 1 0 0 1 1-1h3.5a1 1 0 0 1 1 1c0 1.25.19 2.46.56 3.58a1 1 0 0 1-.25 1.01l-2.19 2.2z"
                />
              </svg>
            </span>
            <span class="min-w-0">
              <span class="block text-sm text-[#D5DDCF]/80">تلفن</span>
              <span dir="ltr" class="mt-2 block whitespace-nowrap text-lg font-bold text-[#FFF8E8]">
                0930 32 36 974
              </span>
            </span>
          </a>

          <a
            href="https://instagram.com/Cafechii__"
            target="_blank"
            rel="noopener noreferrer"
            class="group flex min-h-[100px] items-center gap-4 rounded-xl border border-[#A8B6A3]/40 bg-white/[0.025] px-4 py-4 transition duration-300 hover:border-[#D9BE81]/70 hover:bg-white/[0.05]"
          >
            <span
              class="flex h-14 w-14 shrink-0 items-center justify-center rounded-full bg-[#F4EEDB] text-[#173C2E] transition group-hover:bg-[#D9BE81]"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
                class="h-7 w-7"
                aria-hidden="true"
              >
                <rect x="3" y="3" width="18" height="18" rx="5" />
                <circle cx="12" cy="12" r="4" />
                <circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none" />
              </svg>
            </span>
            <span class="min-w-0">
              <span class="block text-sm text-[#D5DDCF]/80">اینستاگرام</span>
              <span dir="ltr" class="mt-2 block whitespace-nowrap text-lg font-bold text-[#FFF8E8]">
                @Cafechii__
              </span>
            </span>
          </a>

          <a
            href="https://maps.google.com/"
            target="_blank"
            rel="noopener noreferrer"
            class="group flex min-h-[100px] items-center gap-4 rounded-xl border border-[#A8B6A3]/40 bg-white/[0.025] px-4 py-4 transition duration-300 hover:border-[#D9BE81]/70 hover:bg-white/[0.05]"
          >
            <span
              class="flex h-14 w-14 shrink-0 items-center justify-center rounded-full bg-[#F4EEDB] text-[#173C2E] transition group-hover:bg-[#D9BE81]"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="h-7 w-7"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M12 2a7 7 0 0 0-7 7c0 5.25 7 13 7 13s7-7.75 7-13a7 7 0 0 0-7-7Zm0 10a3 3 0 1 1 0-6 3 3 0 0 1 0 6Z"
                  clip-rule="evenodd"
                />
              </svg>
            </span>
            <span class="min-w-0">
              <span class="block text-sm text-[#D5DDCF]/80">آدرس کافه</span>
              <span class="mt-2 flex items-center gap-2 text-base font-bold text-[#FFF8E8]">
                روی نقشه ببینید
                <span aria-hidden="true">←</span>
              </span>
            </span>
          </a>

          <div
            class="flex min-h-[100px] items-center gap-4 rounded-xl border border-[#A8B6A3]/40 bg-white/[0.025] px-4 py-4"
          >
            <span
              class="flex h-14 w-14 shrink-0 items-center justify-center rounded-full bg-[#F4EEDB] text-[#173C2E]"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
                class="h-7 w-7"
                aria-hidden="true"
              >
                <circle cx="12" cy="12" r="9" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 7v5l3 2" />
              </svg>
            </span>
            <span class="min-w-0">
              <span class="block text-sm text-[#D5DDCF]/80">ساعات کاری</span>
              <span class="mt-2 block text-lg font-bold text-[#FFF8E8]">همه روزه</span>
              <span class="mt-1 block text-sm text-[#D5DDCF]/70">منتظر شما هستیم</span>
            </span>
          </div>
        </div>

        <div class="border-t border-[#B7C0A9]/25 px-6 py-5 sm:px-9 lg:px-12">
          <div
            class="flex flex-col justify-between gap-4 text-xs sm:flex-row sm:items-center sm:gap-6 sm:text-sm"
          >
            <div class="flex items-center gap-3 text-[#D9BE81]">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 32 32"
                fill="none"
                stroke="currentColor"
                stroke-width="1.5"
                class="h-7 w-7 shrink-0"
                aria-hidden="true"
              >
                <path d="M5 25C6 13 14 5 27 4c-1 13-8 21-20 22" />
                <path d="M4 28 21 11M11 22c4 0 7 1 9 4" />
              </svg>
              <span class="h-px w-12 bg-[#D9BE81]/70"></span>
              <span class="text-[#F1EBDC]/75">
                ساخته شده وب‌سایت توسط
                <span class="font-bold text-[#FFF5DA]">تیم وندو</span>
              </span>
            </div>

            <p class="text-[#F1EBDC]/75">© 2026 کافه چی. تمامی حقوق محفوظ است.</p>
          </div>
        </div>
      </div>
    </footer>
  </main>
</template>
