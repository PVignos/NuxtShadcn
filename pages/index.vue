<script setup lang="ts">
import HomeCarousel from "~/components/ui/home-carousel/HomeCarousel.vue";
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <main>
      <HomeCarousel />

      <div class="max-w-7xl mx-auto py-6 sm:px-6 lg:px-8">
        <!-- About Section -->
        <section id="about" class="mt-12">
          <h2 class="text-2xl font-semibold text-gray-900 mb-4">
            About Our Property
          </h2>
          <p class="text-gray-600">
            Experience the beauty of Mattinata, Puglia in our charming vacation
            home. With three unique apartments, we offer the perfect retreat for
            families, couples, or groups of friends looking to explore the
            stunning Adriatic coast.
          </p>
        </section>

        <!-- Apartments Section -->
        <section id="apartments" class="mt-12">
          <h2 class="text-2xl font-semibold text-gray-900 mb-4">
            Our Apartments
          </h2>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <div
              v-for="i in 3"
              :key="i"
              class="bg-white rounded-lg shadow-md overflow-hidden"
            >
              <img
                src="/images/placeholder.svg"
                :alt="`Apartment ${i}`"
                class="w-full h-48 object-cover"
              />
              <div class="p-4">
                <h3 class="font-semibold text-lg mb-2">Apartment {{ i }}</h3>
                <p class="text-gray-600">
                  Cozy and comfortable, perfect for your stay in Mattinata.
                </p>
                <button
                  class="mt-4 bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition duration-300"
                >
                  View Details
                </button>
              </div>
            </div>
          </div>
        </section>

        <!-- Location Section -->
        <section id="location" class="mt-12">
          <h2 class="text-2xl font-semibold text-gray-900 mb-4">
            Our Location
          </h2>
          <div class="aspect-w-16 aspect-h-9">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d47736.91999146693!2d16.014699078098687!3d41.70851217130064!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x1337b4308ecd3c6d%3A0x4100fef11c0f9e0!2s71030%20Mattinata%2C%20Province%20of%20Foggia%2C%20Italy!5e0!3m2!1sen!2sus!4v1653835815361!5m2!1sen!2sus"
              width="600"
              height="450"
              style="border: 0"
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              class="w-full h-full rounded-lg shadow-lg"
            />
          </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="mt-12 mb-12">
          <h2 class="text-2xl font-semibold text-gray-900 mb-4">Contact Us</h2>
          <form class="max-w-lg">
            <div class="mb-4">
              <label for="name" class="block text-gray-700 font-bold mb-2"
                >Name</label
              >
              <input
                id="name"
                type="text"
                name="name"
                class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
            <div class="mb-4">
              <label for="email" class="block text-gray-700 font-bold mb-2"
                >Email</label
              >
              <input
                id="email"
                type="email"
                name="email"
                class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
            <div class="mb-4">
              <label for="message" class="block text-gray-700 font-bold mb-2"
                >Message</label
              >
              <textarea
                id="message"
                name="message"
                rows="4"
                class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
            <button
              type="submit"
              class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition duration-300"
            >
              Send Message
            </button>
          </form>
        </section>
      </div>
    </main>
  </div>
</template>
