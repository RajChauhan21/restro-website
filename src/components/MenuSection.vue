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

            <button class="w-full py-2 rounded-xl font-medium
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
export default {

  name: "MenuSection",

  data() {
    return {

      selected: "All",

      categories: ["All", "Western", "Indian", "Drinks"],

      dishes: [

        {
          name: "Margherita Pizza",
          price: 299,
          category: "Western",
          image: "https://images.unsplash.com/photo-1513104890138-7c749659a591?w=800",
          description: "Classic Italian pizza with fresh mozzarella"
        },
        {
          name: "Creamy Pasta",
          price: "249",
          category: "Western",
          image: "https://images.unsplash.com/photo-1555949258-eb67b1ef0ceb?w=800",
          description: "Classic Mexican Pasta with fresh vegetables and cheese"
        },
        {
          name: "Veg Burger",
          price: "179",
          category: "Western",
          image: "https://images.unsplash.com/photo-1550547660-d9450f859349?w=800",
          description: "Experience Mouthwatering Veg Burger with fresh vegetables and cheese"
        },

        {
          name: "Samosa",
          price: 250,
          category: "Indian",
          image: "https://images.unsplash.com/photo-1601050690597-df0568f70950",
          description: "Enjoy hot samosa with tangy chutney"
        },

        {
          name: "Butter Chicken",
          price: 350,
          category: "Indian",
          image: "https://images.unsplash.com/photo-1603894584373-5ac82b2ae398",
          description: "Rich creamy chicken curry"
        },

        {
          name: "Cold Coffee",
          price: 150,
          category: "Drinks",
          image: "https://images.unsplash.com/photo-1509042239860-f550ce710b93",
          description: "Chilled creamy coffee"
        }

      ]

    }
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