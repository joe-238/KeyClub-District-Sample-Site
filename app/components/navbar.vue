<template>
  <nav class="bg-white px-6 py-4 flex items-center justify-between shadow-sm">
    <img
      src="/key_club_logo.png"
      alt="Key Club District logo"
      class="w-24 object-contain"
    />
    <div
      class="relative flex items-center space-x-8 rounded-full border border-slate-200 bg-slate-100 px-3 py-2 shadow-sm"
    >
      <span
        ref="slider"
        class="absolute left-0 top-0 z-0 rounded-full bg-white transition-all duration-300 ease-out"
        :style="pillStyle"
      ></span>

      <!-- Links -->
      <NuxtLink
        v-for="(link, i) in links"
        :key="link.to"
        :to="link.to"
        class="relative z-10 rounded-full px-4 py-2 text-sm font-semibold text-blue-500 transition hover:text-blue-600"
        :ref="(el) => setItemRef(i, el)"
      >
        {{ link.name }}
      </NuxtLink>
    </div>

    <button
      class="inline-flex items-center justify-center rounded-full border border-sky-200 bg-white px-5 py-2 text-sm font-semibold text-sky-600 shadow-sm shadow-slate-200 transition hover:border-sky-300 hover:bg-sky-50"
    >
      Contact Us
    </button>
  </nav>
</template>

<script setup>
import { ref, onMounted, watch, nextTick } from "vue";
import { useRoute } from "vue-router";

const links = [
  { name: "Home", to: "/" },
  { name: "About", to: "/about" },
  { name: "Events", to: "/events" },
  { name: "Resources", to: "/resources" },
];

const slider = ref(null);
const items = ref([]);
const pillStyle = ref({
  width: "60px",
  transform: "translateX(0px)",
});

const route = useRoute();

const setItemRef = (index, el) => {
  if (el) {
    items.value[index] = el.$el || el;
  }
};

const updatePill = async () => {
  await nextTick();
  const index = links.findIndex((l) => l.to === route.path);
  if (index === -1) return;

  const el = items.value[index];
  if (!el) return;

  const parentEl = el.parentElement;
  const topOffset = (parentEl.offsetHeight - el.offsetHeight) / 2;

  pillStyle.value = {
    width: el.offsetWidth + "px",
    height: el.offsetHeight + "px",
    top: topOffset + "px",
    transform: `translateX(${el.offsetLeft}px)`,
  };
};

onMounted(() => {
  setTimeout(updatePill, 100);
});
watch(
  () => route.path,
  () => {
    setTimeout(updatePill, 50);
  },
);
</script>
