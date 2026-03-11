<template>
  <section class="py-20 relative">

    <!-- background glow -->
    <div class="absolute inset-0 -z-10 bg-gradient-to-br from-orange-100 via-red-50 to-yellow-100 blur-3xl opacity-60">
    </div>

    <div class="max-w-7xl mx-auto px-6">

      <!-- Heading -->
      <div class="text-center mb-14" data-aos="fade-up">
        <h2 class="text-4xl font-bold text-gray-800 mb-4">
          Why Choose Our Restaurant
        </h2>
        <p class="text-gray-600 max-w-xl mx-auto">
          We deliver more than just food — we deliver an unforgettable dining experience.
        </p>
      </div>

      <!-- Cards -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">

        <div v-for="service in services" :key="service.title" data-aos="zoom-in" class="group relative backdrop-blur-lg bg-white/70 border border-white/40
        rounded-3xl p-8 shadow-lg transition-all duration-500
        hover:-translate-y-3 hover:shadow-2xl">

          <!-- glowing hover effect -->
          <div
            class="absolute inset-0 rounded-3xl bg-gradient-to-br from-orange-400/10 to-red-400/10 opacity-0 group-hover:opacity-100 transition">
          </div>

          <!-- icon -->
          <div class="w-16 h-16 flex items-center justify-center rounded-2xl
          bg-gradient-to-br from-orange-400 to-red-500
          text-white text-2xl shadow-lg mb-6
          group-hover:scale-110 transition">
            {{ service.icon }}
          </div>

          <h3 class="text-xl font-semibold text-gray-800 mb-3">
            {{ service.title }}
          </h3>

          <p class="text-gray-600 leading-relaxed">
            {{ service.description }}
          </p>

        </div>

      </div>

    </div>
  </section>
</template>

<script>
export default {
  name: "AmenitiesSection",

  data() {
    return {
      services: [
        {
          icon: "🍽️",
          title: "Fine Dining Experience",
          description:
            "Enjoy a luxurious dining atmosphere with elegant interiors and world-class hospitality."
        },
        {
          icon: "🚚",
          title: "Fast Delivery",
          description:
            "Get your favorite dishes delivered fresh and hot directly to your doorstep."
        },
        {
          icon: "🥗",
          title: "Fresh Ingredients",
          description:
            "We use only the freshest locally sourced ingredients for unmatched flavor."
        },
        {
          icon: "👨‍🍳",
          title: "Expert Chefs",
          description:
            "Our experienced chefs craft every dish with passion and perfection."
        },
        {
          icon: "🎉",
          title: "Party & Event Hosting",
          description:
            "Celebrate birthdays, anniversaries, and special events in our elegant dining space."
        },
        {
          icon: "🚗",
          title: "Free Car Parking",
          description:
            "Enjoy hassle-free dining with our spacious and secure free parking available for all guests."
        }
      ]
    };
  }
};
</script>