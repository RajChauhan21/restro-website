<template>

<section class="py-14 px-6 relative overflow-hidden">

  <!-- Background Glow -->

  <div class="absolute -top-40 left-1/2 -translate-x-1/2 w-[600px] h-[600px] bg-orange-200 blur-[140px] opacity-40 -z-10"></div>

  <div class="max-w-7xl mx-auto">

    <!-- Title -->

    <h2 class="text-4xl md:text-5xl font-bold text-center mb-16">
      Our Gallery
    </h2>


    <!-- Gallery Grid -->

    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">

      <div
        v-for="(image, index) in images"
        :key="index"
        data-aos="zoom-in"
        class="group relative overflow-hidden rounded-2xl shadow-lg"
      >

        <!-- Image -->

        <img
          :src="image"
          class="w-full h-56 object-cover transition duration-500 group-hover:scale-110"
        />

        <!-- Gradient Overlay -->

        <div
          class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent opacity-0 group-hover:opacity-100 transition"
        ></div>

      </div>

    </div>

  </div>

</section>

</template>



<script>
import image from '../assets/image.png'
import biryani_gallery from "../assets/biryani_gallery.png";
import mutton_biryani from "../assets/mutton_biryani_gallery.png";
import salad_gallery from "../assets/salad_gallery.png";
import snacks_gallery from "../assets/snacks_gallery.png";
import soup_gallery from "../assets/soup_gallery.png";
import sweet_gallery from "../assets/sweet_gallery.png";
import tandoori from "../assets/tandoori_roti_gallery.png";
import sweet_gallery_1 from "../assets/sweet_gallery_1.png";

export default {
  name: "GallerySection",

  data() {

    return {

      images: [
        biryani_gallery,
        mutton_biryani,
        salad_gallery,
        snacks_gallery,
        soup_gallery,
        sweet_gallery,
        tandoori,
        sweet_gallery_1,
        // "https://images.unsplash.com/photo-1550547660-d9450f859349?w=800",
        // "https://images.unsplash.com/photo-1555949258-eb67b1ef0ceb?w=800",
        // "https://images.unsplash.com/photo-1600891964599-f61ba0e24092?w=800",
        // "https://images.unsplash.com/photo-1540189549336-e6e99c3679fe?w=800",
        // "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=800",
        // "https://images.unsplash.com/photo-1551782450-a2132b4ba21d?w=800",
        // "https://images.unsplash.com/photo-1504674900247-0877df9cc836?w=800"
      ]

    }

  }

}

</script>