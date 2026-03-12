<template>

  <section id="menu" class="py-20 px-6">

    <div class="max-w-7xl mx-auto">

      <!-- Title -->

      <h2 class="text-4xl md:text-5xl font-bold text-center mb-6">
        Our Menu
      </h2>

      <p class="text-center text-gray-600 mb-12">
        Freshly prepared dishes made with premium ingredients
      </p>


      <!-- Category Buttons -->

      <div class="flex flex-wrap justify-center gap-4 mb-14">

        <button v-for="c in categories" :key="c" @click="selected = c" class="px-6 py-2 rounded-full font-medium transition-all duration-300
               backdrop-blur-md border shadow-md
               hover:scale-105 active:scale-95" :class="selected === c
                ? 'bg-gradient-to-r from-orange-400 to-red-500 text-white shadow-lg'
                : 'bg-white/60 hover:bg-orange-100 text-gray-700'">
          {{ c }}
        </button>

      </div>


      <!-- Menu Cards -->

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10">

        <div v-for="dish in filteredDishes" :key="dish.name" data-aos="zoom-in" class="group relative bg-white/60 backdrop-blur-lg rounded-3xl shadow-lg
               overflow-hidden transition-all duration-500
               hover:-translate-y-2 hover:shadow-2xl">

          <!-- Image -->

          <div class="overflow-hidden">

            <img :src="dish.image"
              class="w-full h-52 object-cover transition-transform duration-500 group-hover:scale-110" />

          </div>


          <!-- Content -->

          <div class="p-6">

            <div class="flex justify-between items-center mb-2">

              <h3 class="text-xl font-semibold">
                {{ dish.name }}
              </h3>

              <span class="text-red-500 font-bold text-lg">
                ₹{{ dish.price }}
              </span>

            </div>

            <p class="text-gray-500 text-sm mb-4">
              {{ dish.description }}
            </p>


            <!-- Order Button -->

            <button @click="joinNow(`I want to order ${dish.name}`)" class="relative z-10 w-full py-2 rounded-xl font-medium
                   bg-gradient-to-r from-orange-400 to-red-500
                   text-white transition-all duration-300
                   hover:shadow-lg hover:scale-105 active:scale-95">
              Order Now
            </button>

          </div>


          <!-- Glow Effect -->

          <div class="absolute inset-0 opacity-0 group-hover:opacity-20
                 bg-gradient-to-r from-orange-300 to-red-400
                 blur-2xl transition duration-500"></div>

        </div>

      </div>

    </div>

  </section>

</template>


<script>

import dal from '../assets/dal_menu.png'
import drink from '../assets/drink_menu.png'
import nan from '../assets/nan_menu.png'
import paneer from '../assets/paneer_menu.png'
import rice from '../assets/rice_menu.png'


export default {

  name: "MenuSection",

  data() {
    return {
      message:'',
      selected: "All",

      categories: ["All", "Indian", "Drinks"],

      dishes: [

        {
          name: "Dal Tadka",
          price: 299,
          category: "Indian",
          image: dal,
          description: "Classic Indian dal with spicy tadka"
        },
        {
          name: "Nan Roti",
          price: "50",
          category: "Indian",
          image: nan,
          description: "Fluffy and Heavy Butter Loaded Nan's"
        },
        {
          name: "Paneer Dishes",
          price: "179",
          category: "Indian",
          image: paneer,
          description: "Experience  Mouthwatering Cubed Paneer dishes"
        },

        {
          name: "Rices",
          price: 120,
          category: "Indian",
          image: rice,
          description: "Enjoy various rice dishes with aromatic flavors and spices"
        },

        {
          name: "Butter Chicken",
          price: 350,
          category: "Indian",
          image: "https://images.unsplash.com/photo-1603894584373-5ac82b2ae398",
          description: "Rich creamy chicken curry"
        },

        {
          name: "Cold Drinks",
          price: 150,
          category: "Drinks",
          image: drink,
          description: "Chilled beverages to refresh your plate"
        }
      ]
    }
  },
  methods: {
    joinNow(message) {
      const phone = "918591772677"
      // const message = "Hello, I want to join IronCore Gym. Please share membership details."
      this.message = message;
      const url = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`

      window.open(url, "_blank")
    },
  },
  computed: {

    filteredDishes() {

      if (this.selected === "All") {
        return this.dishes
      }

      return this.dishes.filter(
        dish => dish.category === this.selected
      )

    }

  }

}
</script>