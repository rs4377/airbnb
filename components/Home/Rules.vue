<script setup>
import { ref } from "vue";

const isThingsOpen = ref(false);
const isSaftyOpen = ref(false);

function toggleThings() {
  isThingsOpen.value = !isThingsOpen.value;
  console.log(isThingsOpen.value ? "Opening Things" : "Closing Things");
}

function toggleSafty() {
  isSaftyOpen.value = !isSaftyOpen.value;
  console.log(isSaftyOpen.value ? "Opening Safty" : "Closing Safty");
}
</script>

<template>
  <div class="mb-4 mt-4 w-2/3 px-4">
    <span class="text-xs font-medium text-gray-400"
      >If you’re selected and decide to book, you’ll have 24 hours to complete
      the purchase. Travel costs are not included. Read the
      <span class="underline cursor-pointer">full rules,</span>
      including age and geographical eligibility, how data will be used, odds of
      being selected and other terms.</span
    >
  </div>
  <div class="py-1 w-full border-b border-black/20"></div>

  <div class="w-full max-w-5xl mx-auto px-4 py-6">
    <h2 class="text-2xl font-semibold mb-6 text-center sm:text-left">
      Things to know
    </h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-sm">
      <div class="p-4">
        <h3 class="text-base font-semibold mb-3">The basics</h3>
        <ul class="text-base font-normal space-y-2">
          <li>Check-in after 8:00 pm</li>
          <li>Checkout before 1:00 am</li>
          <li>2 guests maximum</li>
          <li>
            <button @click="toggleThings" class="underline text-base font-bold">
              {{ isThingsOpen ? "Hide <" : "Show more >" }}
            </button>
          </li>
        </ul>
        <transition name="fade" mode="out-in">
          <div
            v-if="isThingsOpen"
            class="mt-4 border border-gray-200 rounded-xl p-4 shadow-inner text-sm bg-gray-50"
          >
            <div class="text-base font-semibold mb-2">More about basics</div>
            <ul class="list-disc list-inside space-y-1">
              <li>Late night check-ins available on request</li>
              <li>Quiet hours after 10 PM</li>
              <li>No outside visitors allowed overnight</li>
              <li>No pets</li>
              <li>No parties or events</li>
              <li>No commercial photography</li>
              <li>No smoking</li>
            </ul>
          </div>
        </transition>
      </div>

      <div class="p-4">
        <h3 class="text-base font-semibold mb-3">Safety & property</h3>
        <ul class="text-base font-normal space-y-2">
          <li>No carbon monoxide alarm</li>
          <li>No smoke alarm</li>
          <li>Exterior security cameras on property</li>
          <li>
            <button @click="toggleSafty" class="underline text-base font-bold">
              {{ isSaftyOpen ? "Hide <" : "Show more >" }}
            </button>
          </li>
        </ul>
        <transition name="fade" mode="out-in">
          <div
            v-if="isSaftyOpen"
            class="mt-4 border border-gray-200 rounded-xl p-4 shadow-inner text-sm bg-gray-50"
          >
            <div class="text-base font-semibold mb-2">
              More about Safety & property
            </div>
            <ul class="list-disc list-inside space-y-1">
              <li>Security footage stored for up to 30 days</li>
              <li>Neighborhood watch zone</li>
              <li>Door locks are electronically managed</li>
              <li>Potential for noise</li>
              <li>No parking on property</li>
              <li>Amenity limitations</li>
              <li>Weapons on property</li>
              <li>Not suitable for children and infants</li>
            </ul>
          </div>
        </transition>
      </div>
    </div>
  </div>
</template>
