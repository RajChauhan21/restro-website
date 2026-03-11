<template>

  <section id="contact" class="py-24 px-6 relative overflow-hidden">

    <!-- Background Glow -->

    <div
      class="absolute -top-40 left-1/2 -translate-x-1/2 w-[600px] h-[600px] bg-orange-200 blur-[140px] opacity-40 -z-10">
    </div>

    <div class="max-w-7xl mx-auto">

      <!-- Section Title -->

      <h2 class="text-4xl md:text-5xl font-bold text-center mb-16">
        Visit Our Restaurant
      </h2>


      <div class="grid lg:grid-cols-3 gap-10 items-start">


        <!-- Google Map -->

        <div data-aos="fade-right" class="lg:col-span-2 rounded-3xl overflow-hidden shadow-2xl border border-white/30">

          <!-- <iframe class="w-full h-[400px]" loading="lazy" src="<iframe src="
            https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3772.3791103707226!2d73.1165631!3d19.0030091!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3be7e9005aa3b43f%3A0xf8406fd69356b43b!2sRoyal%20Seekh!5e0!3m2!1sen!2sin!4v1773233766622!5m2!1sen!2sin"></iframe> -->
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3772.3791103707226!2d73.1165631!3d19.0030091!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3be7e9005aa3b43f%3A0xf8406fd69356b43b!2sRoyal%20Seekh!5e0!3m2!1sen!2sin!4v1773233766622!5m2!1sen!2sin"
            width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>


        <!-- Contact + QR -->

        <div data-aos="fade-left" class="bg-white/70 backdrop-blur-xl p-8 rounded-3xl shadow-xl
               border border-white/30 space-y-6">

          <!-- Contact Details -->

          <div>

            <h3 class="text-2xl font-semibold mb-4">
              Contact Details
            </h3>

            <div class="space-y-3 text-gray-700">

              <p>📍 Office no. 6/7 ,First Floor, Millennium Hilton, Sector 1-S, opp. Dominos Pizza, near D Mart Road,
                New Panvel East, Panvel, Navi Mumbai, Maharashtra 410206</p>

              <p>📞 +91 85917 72677</p>

              <p>✉️ NA</p>

              <p>🕒 12:00 AM – 11:00 PM All Day</p>

            </div>

          </div>


          <!-- Divider -->

          <div class="h-px bg-gray-200"></div>


          <!-- QR Code -->

          <!-- <div class="text-center">

            <h3 class="text-xl font-semibold mb-4">
              Scan to Order
            </h3>

            <img src="https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=https://wa.me/919876543210"
              class="mx-auto rounded-xl shadow-lg" />

            <p class="text-sm text-gray-500 mt-3">
              Scan to order via WhatsApp
            </p>

          </div> -->

        </div>

      </div>

    </div>

  </section>

</template>



<script>

export default {

  name: "ContactVisitSection"

}

</script>