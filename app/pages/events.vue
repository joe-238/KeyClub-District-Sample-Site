<template>
  <section class="min-h-screen bg-white">
    <div class="relative overflow-hidden h-[55vh] sm:h-[60vh] lg:h-[65vh]">
      <Transition name="bg-fade" mode="out-in">
        <img
          :key="currentFeaturedIndex"
          :src="currentFeatured.image"
          alt="Key Club event"
          class="absolute w-full object-cover brightness-75 h-[55vh] sm:h-[60vh] lg:h-[65vh]"
        />
      </Transition>

      <div
        class="relative mx-auto flex h-[48vh] sm:h-[52vh] lg:h-[56vh] max-w-7xl items-center px-4 sm:px-6"
      >
        <Transition
          :name="direction > 0 ? 'slide-right' : 'slide-left'"
          mode="out-in"
        >
          <div :key="currentFeaturedIndex" class="max-w-3xl text-white">
            <span
              class="inline-flex rounded-full bg-sky-500/20 px-3 py-1 text-xs sm:text-sm font-semibold tracking-[0.3em] text-sky-200"
            >
              {{ currentFeatured.badge }}
            </span>

            <h1
              class="mt-6 font-bold tracking-tight text-3xl sm:text-4xl lg:text-5xl"
            >
              {{ currentFeatured.title }}
            </h1>

            <p
              class="mt-6 max-w-xl text-base sm:text-lg leading-7 sm:leading-8 text-slate-200 hidden sm:block"
            >
              {{ currentFeatured.description }}
            </p>

            <div class="mt-8 flex flex-col sm:flex-row flex-wrap gap-4">
              <NuxtLink
                to="/about"
                class="inline-flex justify-center rounded-full bg-sky-500 px-6 py-3 text-sm font-semibold text-white shadow-lg shadow-sky-500/20 transition hover:bg-sky-400"
              >
                Learn More
              </NuxtLink>

              <NuxtLink
                to="/"
                class="inline-flex justify-center rounded-full border border-white/20 bg-white/10 px-6 py-3 text-sm font-semibold text-white transition hover:bg-white/20"
              >
                Back to Home
              </NuxtLink>
            </div>
          </div>
        </Transition>
      </div>

      <div
        class="absolute bottom-6 left-0 right-0 flex items-center justify-center gap-4"
      >
        <button
          @click="prevFeatured"
          class="rounded-full bg-white/20 p-2 text-white transition hover:bg-white/30"
        >
          ‹
        </button>

        <!-- Dots -->
        <div class="flex gap-2">
          <button
            v-for="(item, index) in featured"
            :key="item.id"
            @click="goToFeatured(index)"
            :class="[
              'h-2 rounded-full transition-all duration-300',
              currentFeaturedIndex === index
                ? 'w-8 bg-white'
                : 'w-2 bg-white/50 hover:bg-white/75',
            ]"
          ></button>
        </div>

        <button
          @click="nextFeatured"
          class="rounded-full bg-white/20 p-2 text-white transition hover:bg-white/30"
        >
          ›
        </button>
      </div>
    </div>

    <div class="mx-auto max-w-7xl px-4 sm:px-6 py-12 sm:py-16 lg:py-20">
      <div
        class="rounded-[2rem] border border-slate-200 bg-slate-50 p-6 sm:p-8 lg:p-10 shadow-sm"
      >
        <div class="flex flex-col gap-10 lg:flex-row lg:items-start">
          <div class="w-full lg:flex-[0.8]">
            <p
              class="text-xs sm:text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              What to expect
            </p>

            <h2 class="mt-4 font-bold text-slate-900 text-2xl sm:text-3xl">
              A calendar made for leadership, service, and connection.
            </h2>

            <p class="mt-4 text-slate-600 leading-7 sm:leading-8">
              Discover district events that help officers learn, members serve,
              and clubs grow stronger together.
            </p>
          </div>

          <div
            class="grid w-full gap-4 sm:grid-cols-2 lg:grid-cols-3 lg:flex-1"
          >
            <div class="rounded-3xl bg-white p-6 shadow-sm">
              <h3 class="font-semibold text-slate-900">Leadership</h3>
              <p class="mt-2 text-sm text-slate-600">
                Workshops and officer development.
              </p>
            </div>

            <div class="rounded-3xl bg-white p-6 shadow-sm">
              <h3 class="font-semibold text-slate-900">Service</h3>
              <p class="mt-2 text-sm text-slate-600">
                Community impact projects.
              </p>
            </div>

            <div class="rounded-3xl bg-white p-6 shadow-sm">
              <h3 class="font-semibold text-slate-900">Connection</h3>
              <p class="mt-2 text-sm text-slate-600">
                Networking and collaboration.
              </p>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-12 sm:mt-16 grid gap-8 lg:grid-cols-[1.35fr,0.85fr]">
        <div class="space-y-8">
          <div
            class="rounded-[2rem] border border-slate-200 bg-white p-6 sm:p-8 lg:p-10 shadow-sm"
          >
            <p
              class="text-xs sm:text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              Featured event
            </p>

            <h2 class="mt-4 font-bold text-slate-900 text-2xl sm:text-3xl">
              District Leadership Summit
            </h2>

            <p class="mt-4 text-slate-600 leading-7 sm:leading-8">
              A focused day of leadership development, strategy planning, and
              collaboration.
            </p>

            <div class="mt-8 grid gap-4 sm:grid-cols-3">
              <div class="rounded-3xl border border-slate-200 bg-slate-50 p-5">
                <p class="font-semibold text-slate-900">When</p>
                <p class="mt-2 text-sm text-slate-600">May 15, 2025</p>
              </div>

              <div class="rounded-3xl border border-slate-200 bg-slate-50 p-5">
                <p class="font-semibold text-slate-900">Where</p>
                <p class="mt-2 text-sm text-slate-600">District HQ</p>
              </div>

              <div class="rounded-3xl border border-slate-200 bg-slate-50 p-5">
                <p class="font-semibold text-slate-900">Type</p>
                <p class="mt-2 text-sm text-slate-600">Leadership</p>
              </div>
            </div>
          </div>
        </div>
        <aside
          class="space-y-6 rounded-[2rem] border border-slate-200 bg-slate-50 p-6 sm:p-8 shadow-sm"
        >
          <p
            class="text-xs sm:text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
          >
            Event calendar
          </p>

          <div class="space-y-5">
            <div
              v-for="event in events"
              :key="event.id"
              class="fade-in rounded-3xl border border-slate-200 bg-white p-6"
            >
              <h3 class="text-lg font-bold text-slate-900">
                {{ event.title }}
              </h3>

              <p class="mt-2 text-sm text-slate-600">
                {{ event.description }}
              </p>

              <div class="mt-4 text-sm text-slate-500">
                {{ event.date }} • {{ event.location }}
              </div>
            </div>
          </div>
        </aside>
      </div>
    </div>
  </section>
</template>

<script setup>
const events = [
  {
    id: 1,
    title: "District Leadership Summit",
    description:
      "A full-day workshop focused on developing leadership skills, team building, and strategic planning for club officers.",
    category: "Leadership",
    date: "May 15, 2025",
    location: "District Headquarters",
  },
  {
    id: 2,
    title: "Community Service Day",
    description:
      "Join Key Club members for a district-wide day of service at local parks and community partners.",
    category: "Service",
    date: "June 10, 2025",
    location: "Various Locations",
  },
  {
    id: 3,
    title: "Fellowship Retreat",
    description:
      "An overnight experience designed to strengthen connections, share stories, and celebrate success across clubs.",
    category: "Fellowship",
    date: "July 18-19, 2025",
    location: "Camp Lakeview",
  },
];

const featured = [
  {
    id: 1,
    badge: "Upcoming events",
    title:
      "Join Key Club gatherings that develop leaders and serve our communities.",
    description:
      "Discover a full calendar of district events built around service, fellowship, and leadership growth for clubs across the region.",
    image:
      "https://images.unsplash.com/photo-1521737604893-d14cc237f11d?w=1600&h=800&fit=crop",
  },
  {
    id: 2,
    badge: "Featured Event",
    title: "Leadership Summit 2025 - Transform Your Club.",
    description:
      "Join us for an intensive leadership development program designed to equip club officers with the skills and strategies needed to make a real impact.",
    image:
      "https://images.unsplash.com/photo-1543269865-cbf427effbad?w=1600&h=800&fit=crop",
  },
  {
    id: 3,
    badge: "Special Initiative",
    title: "Service Excellence Across Districts.",
    description:
      "Participate in our district-wide service initiative connecting clubs and amplifying the reach of Key Club's mission in the community.",
    image:
      "https://images.unsplash.com/photo-1522202176988-66273c2fd55f?w=1600&h=800&fit=crop",
  },
];

const currentFeaturedIndex = ref(0);
const direction = ref(1);

const currentFeatured = computed(() => featured[currentFeaturedIndex.value]);

const nextFeatured = () => {
  direction.value = 1;
  currentFeaturedIndex.value =
    (currentFeaturedIndex.value + 1) % featured.length;
};

const prevFeatured = () => {
  direction.value = -1;
  currentFeaturedIndex.value =
    (currentFeaturedIndex.value - 1 + featured.length) % featured.length;
};

const goToFeatured = (index) => {
  direction.value = index > currentFeaturedIndex.value ? 1 : -1;
  currentFeaturedIndex.value = index;
};
</script>

<style scoped>
.slide-right-enter-active,
.slide-right-leave-active,
.slide-left-enter-active,
.slide-left-leave-active {
  transition: transform 0.55s cubic-bezier(0.4, 0, 0.2, 1), opacity 0.35s ease;
}

.slide-right-enter-from {
  transform: translateX(100%);
  opacity: 0;
}
.slide-right-enter-to,
.slide-left-enter-to,
.slide-right-leave-from,
.slide-left-leave-from {
  transform: translateX(0);
  opacity: 1;
}
.slide-right-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}
.slide-left-enter-from {
  transform: translateX(-100%);
  opacity: 0;
}
.slide-left-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
.fade-in {
  animation: fadeInUp 0.6s ease-out;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
