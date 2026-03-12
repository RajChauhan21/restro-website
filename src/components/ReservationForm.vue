<template>

  <section id="reservation" class="py-24 px-6 relative overflow-hidden">

    <!-- Background Glow -->

    <div
      class="absolute -top-40 left-1/2 -translate-x-1/2 w-[600px] h-[600px] bg-orange-200 blur-[140px] opacity-40 -z-10">
    </div>

    <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-16 items-center">


      <!-- LEFT SIDE TEXT -->

      <div data-aos="fade-right">

        <h2 class="text-4xl md:text-5xl font-bold mb-6">
          Reserve Your Table
        </h2>

        <p class="text-gray-600 mb-8 leading-relaxed">
          Enjoy an unforgettable dining experience with freshly prepared dishes,
          cozy ambience, and exceptional service. Book your table in seconds.
        </p>

        <div class="space-y-4 text-gray-700">

          <div class="flex items-center gap-3">
            ⭐ <span>Top Rated Restaurant</span>
          </div>

          <div class="flex items-center gap-3">
            🍽 <span>Freshly Cooked Meals</span>
          </div>

          <div class="flex items-center gap-3">
            🕒 <span>Quick Table Booking</span>
          </div>

        </div>

      </div>



      <!-- RESERVATION FORM -->

      <div data-aos="fade-left" class="bg-white/70 backdrop-blur-xl p-10 rounded-3xl shadow-xl
             border border-white/30">

        <form class="space-y-5" @submit.prevent="reserve">

          <!-- Name -->

          <input v-model="name" type="text" placeholder="Your Name" class="w-full p-3 rounded-xl border border-gray-200
                 focus:outline-none focus:ring-2 focus:ring-orange-400
                 transition" />
          <p v-if="errors.name" class="text-red-500 text-sm">{{ errors.name }}</p>
          <!-- Phone -->

          <input v-model="phone" type="tel" placeholder="Phone Number" class="w-full p-3 rounded-xl border border-gray-200
                 focus:outline-none focus:ring-2 focus:ring-orange-400
                 transition" />
          <p v-if="errors.phone" class="text-red-500 text-sm">{{ errors.phone }}</p>
          <!-- Date -->

          <input v-model="date" :min="today" type="date" class="w-full p-3 rounded-xl border border-gray-200
                 focus:outline-none focus:ring-2 focus:ring-orange-400
                 transition" />
          <p v-if="errors.date" class="text-red-500 text-sm">{{ errors.date }}</p>
          <!-- People -->

          <input v-model="people" type="number" placeholder="Number of Guests" class="w-full p-3 rounded-xl border border-gray-200
                 focus:outline-none focus:ring-2 focus:ring-orange-400
                 transition" />
          <p v-if="errors.people" class="text-red-500 text-sm">{{ errors.people }}</p>
          <!-- Button -->

          <button type="submit" class="w-full py-3 rounded-xl font-semibold text-white
                 bg-gradient-to-r from-orange-400 to-red-500
                 hover:from-orange-500 hover:to-red-600
                 transition-all duration-300
                 hover:shadow-lg hover:scale-[1.02] active:scale-95">
            Reserve via WhatsApp
          </button>

        </form>

      </div>

    </div>

  </section>

</template>



<script>

export default {

  name: "ReservationSection",

  data() {
    return {
      name: "",
      phone: "",
      date: "",
      people: "",
      errors: {
        name: '',
        phone: '',
        date: '',
        people: ''
      },
      today: new Date().toISOString().split('T')[0],
    }
  },

  methods: {

    reserve() {

      // reset errors
      this.errors = {
        name: '',
        phone: '',
        date: '',
        people: ''
      }

      let isValid = true

      // Name validation
      if (!this.name || this.name.trim().length < 3) {
        this.errors.name = "Name must be at least 3 characters"
        isValid = false
      }

      // Phone validation
      const phoneRegex = /^\d{10}$/
      if (!this.phone || !phoneRegex.test(this.phone)) {
        this.errors.phone = "Enter valid 10 digit phone number"
        isValid = false
      }

      // Date validation
      if (!this.date) {
        this.errors.date = "Please select a reservation date"
        isValid = false
      }

      const selectedDate = new Date(this.date)
      const today = new Date()
      today.setHours(0, 0, 0, 0)

      if (selectedDate < today) {
        this.errors.date = "Past dates are not allowed"
        isValid = false
      }

      // Guests validation
      if (!this.people || this.people < 1 || this.people > 7) {
        this.errors.people = "Guests must be between 1 and 7"
        isValid = false
      }

      if (!isValid) return

      const message =
        `Hello Sir/Madam, I would like to reserve a table.

Reservation Details - 
Name: ${this.name},
Phone: ${this.phone},
Date: ${this.date},
Guests: ${this.people}`

      const url = `https://wa.me/918591772677?text=${encodeURIComponent(message)}`

      window.open(url)

      // reset form
      this.name = ''
      this.phone = ''
      this.date = ''
      this.people = ''
    }

  }

}

</script>