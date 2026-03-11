<template>

<section class="py-20 px-6">

  <div class="max-w-7xl mx-auto">

    <!-- Title -->

    <h2 class="text-4xl md:text-5xl font-bold text-center mb-6">
      What Our Customers Say
    </h2>

    <p class="text-center text-gray-600 mb-14">
      Loved by hundreds of food lovers
    </p>


    <!-- Testimonials Grid -->

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">

      <div
        v-for="review in reviews"
        :key="review.name"
        data-aos="fade-up"
        class="group relative bg-white/60 backdrop-blur-lg rounded-3xl shadow-lg
               p-8 transition-all duration-500
               hover:-translate-y-2 hover:shadow-2xl"
      >

        <!-- Glow effect -->

        <div
          class="absolute inset-0 opacity-0 blur-3xl 
            bg-gradient-to-r from-orange-300 to-red-400
            transition-all duration-1000 ease-in-out
            group-hover:opacity-30 group-hover:scale-125"
        ></div>


        <!-- Stars -->

        <div class="flex mb-4 text-yellow-400 text-lg">
          <span v-for="n in review.rating" :key="n">⭐</span>
        </div>


        <!-- Review Text -->

        <p class="text-gray-600 mb-6 italic">
          "{{ review.text }}"
        </p>


        <!-- User Info -->

        <div class="flex items-center gap-4">

          <img
            :src="review.image"
            class="w-12 h-12 rounded-full object-cover border"
          />

          <div>

            <h4 class="font-semibold">
              {{ review.name }}
            </h4>

            <span class="text-sm text-gray-500">
              {{ review.role }}
            </span>

          </div>

        </div>

      </div>

    </div>

  </div>

</section>

</template>



<script>
export default {

name: "TestimonialSection",

data() {

return {

reviews: [

{
name: "Rahul Sharma",
role: "Food Blogger",
rating: 5,
text: "Absolutely amazing food! The flavors are authentic and the ambience is fantastic.",
image: "https://randomuser.me/api/portraits/men/32.jpg"
},

{
name: "Priya Mehta",
role: "Regular Customer",
rating: 5,
text: "One of the best restaurants in the city. Fast service and delicious dishes.",
image: "https://randomuser.me/api/portraits/women/44.jpg"
},

{
name: "Amit Patel",
role: "Local Guide",
rating: 4,
text: "Great taste and quality ingredients. Highly recommend their butter chicken!",
image: "https://randomuser.me/api/portraits/men/65.jpg"
}

]

}

}

}
</script>