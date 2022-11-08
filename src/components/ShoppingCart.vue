<script setup>
import { computed, ref } from 'vue'

const items = ref([
  {
    id: 1,
    name: 'MacBook Pro',
    description: 'Description for MacBook Pro.',
    image: new URL('../assets/macbookpro.jpg', import.meta.url).href,
    price: 349999,
    quantity: 1,
  },
  {
    id: 2,
    name: 'Mac Studio',
    description: 'Description for Mac Studio.',
    image: new URL('../assets/macstudio.jpg', import.meta.url).href,
    price: 399999,
    quantity: 1,
  },
  {
    id: 3,
    name: 'iPhone Pro',
    description: 'Description for iPhone Pro.',
    image: new URL('../assets/iphonepro.jpg', import.meta.url).href,
    price: 99999,
    quantity: 1,
  },
  {
    id: 4,
    name: 'iPad Pro',
    description: 'Description for iPad Pro.',
    image: new URL('../assets/ipadpro.jpg', import.meta.url).href,
    price: 129999,
    quantity: 1,
  },
])

function updateQuantity(event, item) {
  item.quantity = parseInt(event.target.value)
}

function deleteItem(id) {
  items.value = items.value.filter(item => item.id !== id)
}

const numberOfItems = computed(() => {
  return items.value.reduce((prev, curr) => prev + curr.quantity, 0)
})

const subtotal = computed(() => {
  return items.value.reduce(
    (prev, curr) => prev + curr.quantity * curr.price,
    0
  )
})

const tax = computed(() => {
  return Math.round(subtotal.value * 0.13)
})

const total = computed(() => {
  return subtotal.value + tax.value
})
</script>

<template>
  <div v-if="items.length > 0" class="my-5">
    <div class="cart-items-container divide-y divide-gray-300">
      <div
        v-for="item in items"
        :key="item.id"
        class="flex flex-col @lg:flex-row @lg:justify-between justify-start py-2"
      >
        <div class="flex">
          <div class="hidden @lg:block w-16 h-16">
            <img
              :src="item.image"
              alt="item image"
              class="hidden @lg:block w-16 h-16"
            />
          </div>
          <div class="px-3">
            <div>{{ item.name }}</div>
            <div class="mt-2 text-gray-600 leading-tight text-sm">
              {{ item.description }}
            </div>
          </div>
        </div>
        <div class="flex items-center py-3 @lg:py-0">
          <div class="w-16 @lg:w-9 px-5 @lg:px-9">
            <input
              @change="updateQuantity($event, item)"
              type="number"
              class="border border-gray-300 pl-2"
              value="1"
              min="1"
              max="10"
            />
          </div>
          <div class="w-16 @lg:w-9 px-5 @lg:px-9">${{ item.price / 100 }}</div>
          <div class="text-xl pl-16">
            <button @click="deleteItem(item.id)">&times;</button>
          </div>
        </div>
      </div>
    </div>
    <div
      class="grid grid-cols-[120px_120px] justify-end text-right leading-10 my-5 px-2 py-2"
    >
      <div class="uppercase text-gray-500">
        <div># of Items</div>
        <div>Subtotal</div>
        <div>Tax (13%)</div>
        <div class="font-bold">Total</div>
      </div>
      <div>
        <div>{{ numberOfItems }}</div>
        <div>${{ subtotal / 100 }}</div>
        <div>${{ tax / 100 }}</div>
        <div class="font-bold">${{ total / 100 }}</div>
      </div>
    </div>
  </div>

  <div v-else class="my-5">There are no items in your cart.</div>
</template>

<style scoped></style>
