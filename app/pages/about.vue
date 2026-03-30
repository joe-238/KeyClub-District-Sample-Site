<template>
  <section class="min-h-screen bg-gray-50 py-20 px-6">
    <div class="max-w-4xl mx-auto text-center">
      <h1 class="text-4xl font-bold text-blue-600 mb-6">About Our District</h1>
      <p class="text-gray-700 mb-6">
        Key Club is a student-led organization that empowers young people to
        lead, serve, and make a difference in their communities. Our district
        brings together clubs from across the region to collaborate on
        meaningful service projects, leadership development, and friendship.
      </p>
      <img
        src="/image.png"
        alt="Key Club members"
        class="w-full rounded-2xl shadow-lg object-cover"
      />

      <div class="mb-12 w-5/6">
        <h2 class="text-2xl font-semibold mb-3">Reach out with us today</h2>

        <div class="flex items-center justify-center">
          <div
            v-for="(item, index) in info"
            :key="index"
            class="bg-white rounded-xl shadow-lg p-6 flex items-center flex-1 hover:shadow-2xl transition"
          >
            <div class="text-4xl mb-4">{{ item.icon }}</div>
            <div class="flex flex-col">
              <h3 class="font-semibold text-lg mb-1">{{ item.title }}</h3>
              <span class="text-gray-600 text-sm text-center">{{
                item.content
              }}</span>
            </div>
          </div>
        </div>
      </div>

      <div class="mb-12">
        <h2 class="text-2xl font-semibold mb-3">Our Mission</h2>
        <p class="text-gray-600">
          To develop leadership skills, foster a spirit of service, and create
          positive change for communities both locally and globally.
        </p>
      </div>

      <!-- Values Section -->
      <div class="mb-12">
        <h2 class="text-2xl font-semibold mb-3">Our Core Values</h2>
        <ul class="text-gray-600 list-disc list-inside space-y-2">
          <li>Leadership: Encouraging students to take initiative</li>
          <li>Service: Making a meaningful impact in communities</li>
          <li>Fellowship: Building lasting friendships and collaboration</li>
          <li>Character: Acting with integrity and responsibility</li>
        </ul>
      </div>

      <!-- Call to Action -->
      <div>
        <p class="text-gray-700 mb-4">Want to get involved or learn more?</p>
        <NuxtLink
          to="/"
          class="inline-block bg-blue-600 text-white px-6 py-3 rounded-lg font-semibold hover:bg-blue-700 transition"
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
    content: "closeify1@gmail.com",
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
