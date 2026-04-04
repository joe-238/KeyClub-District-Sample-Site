<template>
  <section class="min-h-screen bg-white">
    <div class="relative overflow-hidden h-[65vh]">
      <img
        src="https://images.unsplash.com/photo-1552664730-d307ca884978?w=1600&h=800&fit=crop"
        alt="Resources background"
        class="h-[65vh] absolute w-full object-cover brightness-75"
      />
      <div class="relative mx-auto flex h-[56vh] max-w-7xl items-center px-6">
        <div class="max-w-3xl text-white">
          <span
            class="inline-flex rounded-full bg-blue-500/20 px-3 py-1 text-sm font-semibold tracking-[0.3em] text-blue-200"
          >
            RESOURCES
          </span>
          <h1 class="mt-6 text-4xl font-bold tracking-tight sm:text-5xl">
            Resources
          </h1>
          <p class="mt-6 max-w-xl text-lg leading-8 text-slate-200">
            Access important forms, guides, and resources to help manage your
            Key Club and stay organized with district requirements.
          </p>
        </div>
      </div>
    </div>

    <section class="bg-white px-6 py-20">
      <div class="mx-auto max-w-6xl">
        <div class="mb-12 grid gap-6 lg:grid-cols-2 lg:items-center">
          <div
            class="relative h-96 bg-gradient-to-br from-slate-200 to-slate-300 rounded-2xl overflow-hidden"
          >
            <div
              class="absolute inset-0 flex items-center justify-center text-slate-400"
            >
              <svg
                class="w-24 h-24"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="1"
                  d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                ></path>
              </svg>
            </div>
            <div class="absolute top-4 left-4">
              <span
                class="inline-block bg-red-500 text-white px-3 py-1 rounded text-xs font-semibold"
                >Featured</span
              >
            </div>
          </div>
          <div>
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-slate-500 mb-3"
            >
              Report Forms
            </p>
            <h2 class="text-3xl font-bold tracking-tight text-slate-900 mb-4">
              Monthly Reporting Guide
            </h2>
            <p class="text-lg leading-8 text-slate-600 mb-6">
              Submit key reports throughout the year including monthly activity
              summaries, officer elections, and fundraising results. These forms
              help the district track club progress and ensure transparency
              across all Key Club activities.
            </p>
          </div>
        </div>

        <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
          <div
            v-for="(card, index) in resourceCards"
            :key="index"
            class="group overflow-hidden rounded-2xl border border-slate-200 transition hover:shadow-lg"
          >
            <div
              :class="[
                'relative h-48 overflow-hidden flex items-center justify-center',
                card.bgColor || 'bg-gradient-to-br from-slate-100 to-slate-200',
              ]"
            ></div>
            <div class="p-6">
              <p
                class="text-xs font-semibold uppercase tracking-wider text-slate-500 mb-2"
              >
                {{ card.category }}
              </p>
              <h3 class="text-lg font-bold text-slate-900 mb-3">
                {{ card.title }}
              </h3>
              <p class="text-sm leading-6 text-slate-600 mb-4">
                {{ card.description }}
              </p>
              <a
                :href="card.link"
                class="inline-flex items-center gap-2 text-blue-600 font-semibold text-sm hover:text-blue-700 transition"
              >
                Read more
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<script setup>
const resourceCards = ref([
  {
    category: "Report Form",
    title: "Monthly Report Form",
    description:
      "Submit your club's monthly activities and achievements. Track service hours, member engagement, and key metrics to monitor your club's progress throughout the year.",
    link: "#",
    bgColor: "bg-gradient-to-br from-slate-100 to-slate-200",
    isButton: false,
  },
  {
    category: "Report Form",
    title: "Election Report Form",
    description:
      "Report your club's officer elections and leadership structure. Keep the district updated with your club's new leadership team information.",
    link: "#",
    bgColor: "bg-gradient-to-br from-slate-100 to-slate-200",
    isButton: false,
  },
  {
    category: "Report Form",
    title: "Fundraising Report Form",
    description:
      "Document your club's fundraising initiatives and financial results. Track revenue generated and project details for financial reporting.",
    link: "#",
    bgColor: "bg-blue-500",
    isButton: true,
    buttonText: "Access Form",
  },
  {
    category: "Guide",
    title: "Club Officer Handbook",
    description:
      "Comprehensive resource for club leaders covering best practices, meeting management, and leadership strategies.",
    link: "#",
    bgColor: "bg-gradient-to-br from-slate-100 to-slate-200",
    isButton: false,
  },
  {
    category: "Guide",
    title: "Service Project Planning",
    description:
      "Learn how to plan and execute impactful service projects that make a difference in your community.",
    link: "#",
    bgColor: "bg-gradient-to-br from-slate-100 to-slate-200",
    isButton: false,
  },
  {
    category: "Resources",
    title: "District Calendar",
    description:
      "Important dates, deadlines, and Key Club events throughout the year. Stay informed and never miss a deadline.",
    link: "#",
    bgColor: "bg-gradient-to-br from-slate-100 to-slate-200",
    isButton: false,
  },
]);
</script>

<style scoped>
/* Additional styles if needed */
</style>
