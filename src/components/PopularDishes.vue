<script setup>
const dishes = [
{
name: "Margherita Pizza",
price: "₹299",
img: "https://images.unsplash.com/photo-1601924928376-1a03f6c4a4a6"
},
{
name: "Burger",
price: "₹199",
img: "https://images.unsplash.com/photo-1550547660-d9450f859349"
},
{
name: "Pasta",
price: "₹249",
img: "https://images.unsplash.com/photo-1525755662778-989d0524087e"
}
]
</script>

<template>
<section class="py-20 bg-gray-100">

<h2 class="text-4xl text-center font-bold mb-12">
Popular Dishes
</h2>

<div class="grid md:grid-cols-3 gap-8 px-10">

<div
v-for="dish in dishes"
:key="dish.name"
class="bg-white rounded-xl shadow-lg overflow-hidden">

<img :src="dish.img" class="h-60 w-full object-cover">

<div class="p-6">

<h3 class="text-xl font-semibold">
{{ dish.name }}
</h3>

<p class="text-red-500 font-bold mt-2">
{{ dish.price }}
</p>

</div>

</div>

</div>

</section>
</template>