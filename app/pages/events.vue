<template>
  <section class="min-h-screen bg-white">
    <div class="relative overflow-hidden h-[65vh]">
      <img
        src="/image.png"
        alt="Key Club event"
        class="h-[65vh] absolute w-full object-cover brightness-75"
      />
      <div class="relative mx-auto flex h-[56vh] max-w-7xl items-center px-6">
        <div class="max-w-3xl text-white">
          <span
            class="inline-flex rounded-full bg-sky-500/20 px-3 py-1 text-sm font-semibold tracking-[0.3em] text-sky-200"
          >
            Upcoming events
          </span>
          <h1 class="mt-6 text-4xl font-bold tracking-tight sm:text-5xl">
            Join Key Club gatherings that develop leaders and serve our
            communities.
          </h1>
          <p class="mt-6 max-w-xl text-lg leading-8 text-slate-200">
            Discover a full calendar of district events built around service,
            fellowship, and leadership growth for clubs across the region.
          </p>
          <div class="mt-8 flex flex-wrap gap-4">
            <NuxtLink
              to="/about"
              class="inline-flex rounded-full bg-sky-500 px-6 py-3 text-sm font-semibold text-white shadow-lg shadow-sky-500/20 transition hover:bg-sky-400"
            >
              Learn More
            </NuxtLink>
            <NuxtLink
              to="/"
              class="inline-flex rounded-full border border-white/20 bg-white/10 px-6 py-3 text-sm font-semibold text-white transition hover:bg-white/20"
            >
              Back to Home
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>

    <div class="mx-auto max-w-7xl px-6 py-20">
      <div
        class="rounded-[2rem] border border-slate-200 bg-slate-50 p-10 shadow-sm"
      >
        <div
          class="flex flex-col gap-10 lg:flex-row lg:items-center lg:justify-between"
        >
          <div class="max-w-2xl">
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              What to expect
            </p>
            <h2 class="mt-4 text-3xl font-bold text-slate-900">
              A calendar built for leadership, service, and club connection.
            </h2>
            <p class="mt-4 text-slate-600 leading-8">
              Explore district-wide events designed to help officers grow,
              members serve, and clubs collaborate with purpose.
            </p>
          </div>
          <div class="grid gap-4 sm:grid-cols-2 lg:w-[420px]">
            <div class="rounded-3xl bg-white p-6 shadow-sm">
              <h3 class="font-semibold text-slate-900">Leadership</h3>
              <p class="mt-2 text-sm text-slate-600">
                Workshops, planning sessions, and officer development.
              </p>
            </div>
            <div class="rounded-3xl bg-white p-6 shadow-sm">
              <h3 class="font-semibold text-slate-900">Service</h3>
              <p class="mt-2 text-sm text-slate-600">
                Community projects that make a real impact.
              </p>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-16 grid gap-8 lg:grid-cols-[1.35fr,0.85fr]">
        <div class="space-y-8">
          <div
            class="rounded-[2rem] border border-slate-200 bg-white p-10 shadow-sm"
          >
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              Featured event
            </p>
            <h2 class="mt-4 text-3xl font-bold text-slate-900">
              District Leadership Summit
            </h2>
            <p class="mt-4 text-slate-600 leading-8">
              A focused day of leadership development, strategy planning, and
              district collaboration for club officers and advisors.
            </p>
            <div class="mt-8 grid gap-4 sm:grid-cols-3">
              <div class="rounded-3xl border border-slate-200 bg-slate-50 p-5">
                <p class="font-semibold text-slate-900">When</p>
                <p class="mt-2 text-sm text-slate-600">May 15, 2025</p>
              </div>
              <div class="rounded-3xl border border-slate-200 bg-slate-50 p-5">
                <p class="font-semibold text-slate-900">Where</p>
                <p class="mt-2 text-sm text-slate-600">District Headquarters</p>
              </div>
              <div class="rounded-3xl border border-slate-200 bg-slate-50 p-5">
                <p class="font-semibold text-slate-900">Type</p>
                <p class="mt-2 text-sm text-slate-600">Leadership</p>
              </div>
            </div>
          </div>

          <div class="grid gap-6 md:grid-cols-2">
            <article
              class="rounded-[2rem] border border-slate-200 bg-white p-8 shadow-sm"
            >
              <p
                class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
              >
                Highlights
              </p>
              <ul class="mt-6 space-y-3 text-slate-600">
                <li class="flex gap-3">
                  <span
                    class="mt-2 inline-block h-2.5 w-2.5 rounded-full bg-sky-600"
                  ></span>
                  Hands-on leadership workshops.
                </li>
                <li class="flex gap-3">
                  <span
                    class="mt-2 inline-block h-2.5 w-2.5 rounded-full bg-sky-600"
                  ></span>
                  District networking and mentorship.
                </li>
                <li class="flex gap-3">
                  <span
                    class="mt-2 inline-block h-2.5 w-2.5 rounded-full bg-sky-600"
                  ></span>
                  Actionable planning for club goals.
                </li>
              </ul>
            </article>
            <article
              class="rounded-[2rem] border border-slate-200 bg-white p-8 shadow-sm"
            >
              <p
                class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
              >
                Why attend?
              </p>
              <p class="mt-6 text-slate-600 leading-8">
                Connect with other clubs, grow your leadership skills, and
                return with new ideas for meaningful service in your community.
              </p>
            </article>
          </div>
        </div>

        <aside
          class="space-y-6 rounded-[2rem] border border-slate-200 bg-slate-50 p-8 shadow-sm"
        >
          <p
            class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
          >
            Event calendar
          </p>
          <div class="space-y-5">
            <div
              v-for="event in events"
              :key="event.id"
              class="rounded-3xl border border-slate-200 bg-white p-6 transition hover:border-sky-300 hover:shadow-md"
            >
              <div class="flex items-start justify-between gap-4">
                <div>
                  <span
                    class="inline-flex rounded-full bg-sky-100 px-3 py-1 text-sm font-semibold text-sky-600"
                    >{{ event.category }}</span
                  >
                  <h3 class="mt-4 text-xl font-bold text-slate-900">
                    {{ event.title }}
                  </h3>
                </div>
                <span class="text-sm text-slate-500">{{ event.date }}</span>
              </div>
              <p class="mt-4 text-slate-600">{{ event.description }}</p>
              <div
                class="mt-6 flex items-center justify-between text-sm text-slate-500"
              >
                <span>{{ event.location }}</span>
                <NuxtLink
                  to="/about"
                  class="rounded-full bg-sky-600 px-4 py-2 text-sm font-semibold text-white transition hover:bg-sky-700"
                >
                  Details
                </NuxtLink>
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
</script>

<style scoped></style>
