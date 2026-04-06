<template>
  <div class="min-h-screen bg-white py-10 px-4">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-3xl md:text-4xl font-bold text-center mb-10">
        Contact Us
      </h1>
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
        <div class="bg-slate-50 shadow-lg rounded-2xl p-6 md:p-8">
          <h2 class="text-2xl font-semibold mb-6">Send Us a Message</h2>

          <form @submit.prevent="submitForm" class="space-y-5">
            <div>
              <label class="block text-sm font-medium mb-1"> Your Name </label>

              <input
                v-model="form.name"
                type="text"
                placeholder="Enter your name"
                required
                class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>

            <!-- Phone -->
            <div>
              <label class="block text-sm font-medium mb-1">
                Phone Number
              </label>

              <input
                v-model="form.phone"
                type="tel"
                placeholder="Enter your phone number"
                required
                class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
            <div>
              <label class="block text-sm font-medium mb-1">
                Email Address
              </label>

              <input
                v-model="form.email"
                type="email"
                placeholder="Enter your email"
                required
                class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
            <div>
              <label class="block text-sm font-medium mb-1"> Message </label>

              <textarea
                v-model="form.message"
                rows="5"
                placeholder="Write your message..."
                required
                class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
              ></textarea>
            </div>
            <button
              type="submit"
              class="w-full bg-blue-600 text-white py-3 rounded-lg font-medium hover:bg-blue-700 transition"
            >
              Send Message
            </button>
          </form>
        </div>
        <div class="bg-slate-50 shadow-lg rounded-2xl p-6 md:p-8 flex flex-col">
          <h2 class="text-2xl font-semibold mb-4 text-center md:text-left">
            Key Club District Locations
          </h2>
          <p class="text-slate-600 mb-4 text-center md:text-left">
            Find our clubs and district offices on the map below. Click and
            explore for more details.
          </p>

          <!-- Google Map -->
          <div
            class="w-full h-[300px] md:h-[400px] rounded-xl overflow-hidden border border-slate-200"
          >
            <iframe
              class="w-full h-full"
              loading="lazy"
              allowfullscreen
              referrerpolicy="no-referrer-when-downgrade"
              src="https://www.google.com/maps/d/embed?mid=1vXC4_twuPi5LL9RT6gOM_SlQDJmFKs1l&ehbc=2E312F"
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const form = ref({
  name: "",
  phone: "",
  email: "",
  message: "",
});

const submitForm = () => {
  //console.log("Form submitted:", form.value);
  form.value = {
    name: "",
    phone: "",
    email: "",
    message: "",
  };
};
</script>
