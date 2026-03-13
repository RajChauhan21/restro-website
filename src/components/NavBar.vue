<template>

  <header :class="[
    'fixed w-full top-0 z-50 transition-all duration-300',
    scrolled ? 'bg-white/70 backdrop-blur-xl shadow-md' : 'bg-transparent'
  ]">

    <nav class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">

      <!-- Logo -->

      <!-- <div class="text-2xl font-bold bg-gradient-to-r from-orange-500 to-red-500 bg-clip-text text-transparent">
      Royal Seekh
    </div> -->
      <div class="flex items-center gap-3">

        <img src="../assets/canva_logo_rs.png" alt="Royal Seekh Logo" class="h-10 w-auto object-contain" />

        <span class="text-2xl font-bold bg-gradient-to-r from-red-500 to-red-500 bg-clip-text text-transparent">
          Royal Seekh
        </span>

      </div>


      <!-- Desktop Menu -->

      <ul class="hidden md:flex items-center gap-8 font-medium">

        <li>
          <a href="#hero" class="nav-link">Home</a>
        </li>

        <li>
          <a href="#menu" class="nav-link">Menu</a>
        </li>

        <li>
          <a href="#reservation" class="nav-link">Reservation</a>
        </li>

        <li>
          <a href="#contact" class="nav-link">Contact</a>
        </li>

        <!-- WhatsApp Button -->

        <li>

          <a href="https://wa.me/918591772677" class="px-5 py-2 rounded-full text-white font-semibold
                 bg-gradient-to-r from-red-400 to-red-500
                 hover:from-red-500 hover:to-red-600
                 transition-all duration-300 hover:shadow-lg">
            Order Now
          </a>

        </li>

      </ul>


      <!-- Mobile Menu Button -->

      <button @click="toggleMenu" class="md:hidden text-2xl">
        ☰
      </button>

    </nav>


    <!-- Mobile Menu -->

    <div v-if="mobileMenu" class="md:hidden bg-white/90 backdrop-blur-xl shadow-lg">

      <ul class="flex flex-col items-center py-6 gap-6">

        <li><a href="#hero" @click="toggleMenu">Home</a></li>
        <li><a href="#menu" @click="toggleMenu">Menu</a></li>
        <li><a href="#reservation" @click="toggleMenu">Reservation</a></li>
        <li><a href="#contact" @click="toggleMenu">Contact</a></li>

        <li>
          <a href="https://wa.me/919876543210" class="px-6 py-2 rounded-full text-white
                 bg-gradient-to-r from-orange-400 to-red-500">
            Order Now
          </a>
        </li>

      </ul>

    </div>

  </header>

</template>



<script>

export default {

  name: "NavBar",

  data() {
    return {
      mobileMenu: false,
      scrolled: false
    }
  },

  methods: {

    toggleMenu() {
      this.mobileMenu = !this.mobileMenu
    },

    handleScroll() {
      this.scrolled = window.scrollY > 50
    }

  },

  mounted() {
    window.addEventListener("scroll", this.handleScroll)
  },

  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll)
  }

}

</script>



<style>
.nav-link {
  position: relative;
  transition: 0.3s;
}

.nav-link::after {
  content: "";
  position: absolute;
  width: 0%;
  height: 2px;
  left: 0;
  bottom: -4px;
  background: linear-gradient(to right, #f97316, #ef4444);
  transition: 0.3s;
}

.nav-link:hover::after {
  width: 100%;
}
</style>