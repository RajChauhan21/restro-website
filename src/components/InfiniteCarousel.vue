<template>
    <section class="py-12 overflow-hidden">

        <!-- Heading -->
        <div class="text-center mb-10">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-800">
                Experience Our Beautiful Ambience
            </h2>
            <p class="text-gray-600 mt-2">
                Where delicious food meets elegant interiors.
            </p>
        </div>

        <!-- Carousel -->
        <div class="relative w-full overflow-hidden">

            <div class="carousel-track flex gap-6">

                <div v-for="(img, index) in duplicatedImages" :key="index" class="carousel-item">
                    <img :src="img" class="w-full h-full object-cover rounded-2xl shadow-lg" />
                </div>

            </div>

        </div>

    </section>
</template>

<script>
import carousel_1 from '../assets/carousel_1.png';
import carousel_2 from '../assets/carousel_2.png';
import carousel_3 from '../assets/carousel_3.png';
import carousel_4 from '../assets/carousel_4.png';
import carousel_5 from '../assets/carousel_5.png';

export default {
  name: "ImageCarousel",

  data() {
    return {
      images: [
        carousel_1,
        carousel_2,
        carousel_3,
        carousel_4,
        carousel_5
      ]
    };
  },

  computed: {
    duplicatedImages() {
      return [...this.images, ...this.images];
    }
  }
};
</script>

<style scoped>
.carousel-track {
    width: max-content;
    animation: scroll 15s linear infinite;
}

.carousel-item {
    min-width: 220px;
    height: 250px;
}

@media (min-width:768px) {
    .carousel-item {
        min-width: 250px;
        height: 280px;
    }
}

@keyframes scroll {
    0% {
        transform: translateX(0);
    }

    100% {
        transform: translateX(-50%);
    }
}

.carousel-track:hover {
    animation-play-state: paused;
}
</style>