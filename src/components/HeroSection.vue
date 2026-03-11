<template>
    <section id="hero" class="relative min-h-[70vh] md:min-h-screen flex items-center justify-center overflow-hidden">

        <!-- Blurred background -->
        <div class="absolute inset-0 bg-cover bg-[top_right] md:bg-top" :style="{ backgroundImage: `url(${heroBg})` }">
        </div>

        <!-- Dark overlay -->
        <div class="absolute inset-0 bg-black/50"></div>

        <!-- Content -->
        <div class="relative max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-2 gap-10 items-center">

            <!-- LEFT TEXT -->
            <div class="text-white text-center md:text-left">

                <h1 class="text-3xl md:text-5xl font-bold mb-6 leading-tight">
                    Delicious Food <span class="text-orange-400">Delivered Fresh</span>
                </h1>

                <p class="text-gray-200 mb-6 max-w-lg mx-auto md:mx-0 md:mt-19 md:text-lg">
                    Experience authentic flavors crafted with love and fresh ingredients.
                </p>

                <!-- <button to="#menu" class="px-6 py-3 rounded-full font-semibold
        bg-gradient-to-r from-orange-400 to-red-500
        hover:scale-105 transition">
                    Explore Menu
                </button> -->
                <a href="#menu" class="px-6 py-3 rounded-full font-semibold
   bg-gradient-to-r from-orange-400 to-red-500
   hover:scale-105 transition inline-block">
                    Explore Menu
                </a>

            </div>

            <!-- RIGHT IMAGE -->
            <div class="flex justify-center md:justify-end">

                <img :src="heroImage" class="rounded-3xl shadow-2xl w-64 sm:w-80 md:w-full max-w-md object-cover" />

            </div>

        </div>

    </section>

</template>

<script>
import heroImage from '../assets/image.png';
export default {
    name: "HeroSection",
    data() {
        return {
            heroBg: new URL('../assets/image.png', import.meta.url).href
        }
    }
}
</script>