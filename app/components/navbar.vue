<template>
  <nav class="bg-white shadow-sm px-6 py-4 flex justify-between items-center">
    <h1 class="text-xl font-bold text-blue-600">Key Club District</h1>

    <!-- Nav links container must be relative -->
    <div
      class="relative flex space-x-10 text-sm font-medium bg-gray-200 py-2 pr-7 rounded-full"
    >
      <!-- Sliding pill -->
      <span
        ref="slider"
        class="absolute bg-white rounded-full transition-all duration-300 ease-out z-0"
        :style="pillStyle"
      ></span>

      <!-- Links -->
      <NuxtLink
        v-for="(link, i) in links"
        :key="link.to"
        :to="link.to"
        class="relative px-3 py-1 rounded-full z-10 hover:text-blue-500"
        :ref="(el) => setItemRef(i, el)"
      >
        {{ link.name }}
      </NuxtLink>
    </div>

    <button class="px-4 py-2 bg-blue-500 text-white rounded">Contact Us</button>
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
