<template>

    <footer class="relative mt-20 text-white overflow-hidden">

        <!-- Background -->
        <div class="absolute inset-0 bg-gradient-to-br from-gray-900 via-gray-800 to-black"></div>

        <!-- Glow effects -->
        <div class="absolute -top-40 -left-40 w-96 h-96 bg-orange-500/20 blur-3xl rounded-full"></div>
        <div class="absolute -bottom-40 -right-40 w-96 h-96 bg-red-500/20 blur-3xl rounded-full"></div>

        <div class="relative max-w-7xl mx-auto px-6 py-16">

            <div class="grid md:grid-cols-3 gap-12">

                <!-- Brand -->

                <div>

                    <div class="flex items-center gap-3 mb-4">

                        <img :src="logo" class="h-10" />

                        <h2
                            class="text-2xl font-bold bg-gradient-to-r from-red-400 to-red-500 bg-clip-text text-transparent">
                            Royal Seekh
                        </h2>

                    </div>

                    <p class="text-gray-400 leading-relaxed max-w-sm">
                        A place where authentic flavors meet a cozy dining experience.
                        Enjoy delicious food crafted with passion and fresh ingredients.
                    </p>

                </div>


                <!-- Quick Links -->

                <div>

                    <h3 class="font-semibold text-lg mb-4">Quick Links</h3>

                    <ul class="space-y-3 text-gray-400">

                        <li><a href="#hero" class="footer-link">Home</a></li>
                        <li><a href="#menu" class="footer-link">Menu</a></li>
                        <li><a href="#gallery" class="footer-link">Gallery</a></li>
                        <li><a href="#reservation" class="footer-link">Reservation</a></li>

                    </ul>

                </div>


                <!-- Opening Hours -->

                <div>

                    <h3 class="font-semibold text-lg mb-4">Opening Hours</h3>

                    <ul class="space-y-2 text-gray-400">

                        <li>Mon - Fri : 10:00 AM - 11:00 PM</li>
                        <li>Saturday : 11:00 AM - 12:00 AM</li>
                        <li>Sunday : 11:00 AM - 12:00 AM</li>

                    </ul>

                </div>

            </div>


            <!-- Bottom bar -->

            <div
                class="border-t border-gray-700 mt-12 pt-6 flex flex-col md:flex-row items-center justify-between text-gray-400">

                <p>
                    © {{ year }} Royal Seekh. All rights reserved.
                </p>

                <!-- Social icons -->

                <div class="flex gap-6 mt-4 md:mt-0">

                    <a href="#" class="social-icon">📸</a>
                    <a href="#" class="social-icon">👍</a>
                    <a href="#" class="social-icon">🐦</a>

                </div>

            </div>

        </div>

    </footer>

</template>


<script>

import logo from "../assets/canva_logo_rs.png"

export default {

    name: "FooterSection",

    data() {
        return {
            logo,
            year: new Date().getFullYear()
        }
    }

}

</script>


<style scoped>
.footer-link {
    position: relative;
    transition: 0.3s;
}

.footer-link:hover {
    color: white;
}

.footer-link::after {
    content: "";
    position: absolute;
    width: 0%;
    height: 2px;
    left: 0;
    bottom: -3px;
    background: linear-gradient(to right, #fb923c, #ef4444);
    transition: 0.3s;
}

.footer-link:hover::after {
    width: 100%;
}

.social-icon {
    font-size: 20px;
    transition: 0.3s;
}

.social-icon:hover {
    transform: scale(1.25);
}
</style>