<template>
  <section class="min-h-screen bg-white py-20 px-6">
    <div class="mx-auto max-w-6xl">
      <div class="grid gap-10 lg:grid-cols-[1.4fr,0.8fr] lg:items-start">
        <div class="space-y-10">
          <div>
            <p
              class="mb-4 text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              About the district
            </p>
            <h1
              class="text-4xl font-bold tracking-tight text-slate-900 sm:text-5xl"
            >
              A focused district strategy for leadership, service, and impact.
            </h1>
            <p class="mt-6 max-w-3xl text-lg leading-8 text-slate-600">
              We bring clubs together around a clear mission: empower students
              with the support, training, and service opportunities they need to
              lead confidently and serve meaningfully.
            </p>
          </div>

          <div
            class="rounded-3xl border border-slate-200 bg-slate-50 p-10 shadow-sm"
          >
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-slate-500"
            >
              What we prioritize
            </p>
            <h2 class="mt-4 text-3xl font-bold text-slate-900">
              One strong focus, one shared direction.
            </h2>
            <p class="mt-6 text-slate-600 leading-8">
              Our district works with clubs, advisors, and community partners to
              make sure every initiative is purposeful, every leader is
              supported, and every service project creates real value.
            </p>
            <ul class="mt-8 space-y-4 text-slate-600">
              <li class="flex gap-3">
                <span
                  class="mt-1 inline-block h-2.5 w-2.5 rounded-full bg-sky-600"
                ></span>
                Clear leadership development for every member.
              </li>
              <li class="flex gap-3">
                <span
                  class="mt-1 inline-block h-2.5 w-2.5 rounded-full bg-sky-600"
                ></span>
                Project planning that matches local needs and student passion.
              </li>
              <li class="flex gap-3">
                <span
                  class="mt-1 inline-block h-2.5 w-2.5 rounded-full bg-sky-600"
                ></span>
                Better communication across clubs, advisors, and district
                leadership.
              </li>
            </ul>
          </div>

          <div
            class="rounded-3xl border border-slate-200 bg-white p-10 shadow-sm"
          >
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              Our mission
            </p>
            <h2 class="mt-4 text-3xl font-bold text-slate-900">
              Empower student leaders through purposeful service.
            </h2>
            <p class="mt-6 text-slate-600 leading-8">
              We support clubs with mentorship, training, and district-wide
              collaboration so students can build confidence, develop character,
              and make a measurable difference in their communities.
            </p>
          </div>
        </div>

        <aside class="space-y-8">
          <div
            class="rounded-3xl border border-slate-200 bg-white p-8 shadow-sm"
          >
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              Quick overview
            </p>
            <div class="mt-6 space-y-4 text-slate-600">
              <div>
                <p class="font-semibold text-slate-900">District coverage</p>
                <p class="mt-1 text-sm">
                  Serving clubs across the region with coordinated support.
                </p>
              </div>
              <div>
                <p class="font-semibold text-slate-900">Primary goal</p>
                <p class="mt-1 text-sm">
                  Create consistent leadership growth and meaningful community
                  service.
                </p>
              </div>
              <div>
                <p class="font-semibold text-slate-900">Why it matters</p>
                <p class="mt-1 text-sm">
                  Every student should have the tools to lead, serve, and
                  succeed.
                </p>
              </div>
            </div>
          </div>

          <div
            class="rounded-3xl border border-slate-200 bg-white p-8 shadow-sm"
          >
            <p
              class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
            >
              Contact
            </p>
            <h3 class="mt-4 text-2xl font-bold text-slate-900">
              Reach our district team
            </h3>
            <p class="mt-4 text-slate-600">
              If you have questions about membership, events, or service
              projects, we’re here to help.
            </p>
            <div class="mt-8 space-y-4">
              <div
                v-for="(item, index) in info"
                :key="index"
                class="rounded-3xl border border-slate-200 bg-slate-50 p-5"
              >
                <p class="font-semibold text-slate-900">{{ item.title }}</p>
                <p class="mt-2 text-sm text-slate-600">{{ item.content }}</p>
              </div>
            </div>
          </div>
        </aside>
      </div>

      <div
        class="rounded-3xl border border-slate-200 bg-white p-10 text-center shadow-sm mt-10"
      >
        <p
          class="text-sm font-semibold uppercase tracking-[0.3em] text-sky-600"
        >
          Ready to get involved?
        </p>
        <h2 class="mt-4 text-3xl font-bold text-slate-900">
          Join the district movement.
        </h2>
        <p class="mt-4 text-slate-600">
          Discover the support and service opportunities available to your club
          and members.
        </p>
        <NuxtLink
          to="/"
          class="mt-8 inline-flex rounded-full bg-sky-600 px-8 py-3 text-base font-semibold text-white shadow-lg shadow-sky-200 transition hover:bg-sky-700"
        >
          Back to Home
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
const info = [
  {
    icon: "📧",
    title: "Email",
    content: "keyclub@nydkc.com",
  },
  {
    icon: "📞",
    title: "Phone",
    content: "+1 (123) 456-7890",
  },
  {
    icon: "🏠",
    title: "Address",
    content: "Suite 400, New York, USA",
  },
];
</script>

<style scoped>
/* Optional: custom styles can go here */
</style>
