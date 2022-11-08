<script setup>
import { ref } from 'vue'
import ShoppingCart from './components/ShoppingCart.vue'

let isOpen = ref(false)

function toggleShoppingCart() {
  isOpen.value = !isOpen.value
}
</script>

<template>
  <header class="bg-blue-800 text-white px-5 py-6">
    <nav class="flex justify-between">
      <ul class="flex relative gap-4">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
      <ul class="flex relative gap-4">
        <li>
          <a href="#" @click.prevent="toggleShoppingCart">Cart</a>
          <div class="absolute right-0 bg-white border border-gray-300 rounded-md w-80 text-gray-800 z-10" v-show="isOpen">
            <ShoppingCart />
          </div>
        </li>
      </ul>
    </nav>
  </header>
  <div class="container mx-auto mt-5 px-8">
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nemo molestias
    minima impedit vel fuga minus natus quod architecto magni voluptates atque
    consequuntur ea eum, provident, quidem facilis, porro excepturi veritatis
    quibusdam. Inventore harum impedit magni minus quia laudantium obcaecati
    necessitatibus molestiae dolores fugiat sapiente eveniet, culpa a,
    aspernatur saepe non quisquam enim temporibus! Omnis dolorem, nobis
    distinctio consequuntur rem corporis.
    <ShoppingCart />
  </div>
</template>
