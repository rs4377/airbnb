<script setup>
import { ref } from "vue";
import { Mail, CircleCheck, SquareUserRound } from "lucide-vue-next";

const isModalOpen = ref(false);

function openModal() {
  console.log("Opening modal...");
  isModalOpen.value = true;
}

function closeModal() {
  console.log("Closing modal...");
  isModalOpen.value = false;
}

const items = [
  {
    id: 1,
    gift: "/images/gift.png",
  },
];
</script>

<template>
  <div class="text-2xl font-semibold text-black mt-4">
    Where you'll be
    <p class="text-base font-normal mt-4">Rome, Lazio, Italy</p>
  </div>

  <div class="p-4 md:w-full">
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m23!1m12!1m3!1d121795.83098787008!2d78.30045023899203!3d17.453983145538086!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!4m8!3e6!4m0!4m5!1s0x68217581db45eb5b%3A0xb67c0c009144a973!2sUX%20Crafts%2C%20Venkat%20Surabhi%20Plaza%2C%201A%2C%20beside%20Cyber%20Towers%20Flyover%2C%20opp.%20Tata%20Motors%2C%20Surya%20Enclave%2C%20Madhapur%2C%20Hyderabad%2C%20Telangana%20500081!3m2!1d17.4540001!2d78.382852!5e0!3m2!1sen!2sin!4v1747304246991!5m2!1sen!2sin"
      width="700"
      height="500"
      class="w-full rounded-3xl"
      style="border: 0"
      allowfullscreen=""
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
    ></iframe>
  </div>

  <div class="p-4 text-sm font-medium text-gray-800">
    We verified that this listing’s location is accurate.

    <button
      @click="openModal"
      class="underline text-blue-600 font-bold cursor-pointer"
    >
      Learn more
    </button>
    <div
      class="p-4 lg:w-1/2 border-b border-black/20 mt-6 flex items-center gap-1"
    ></div>
  </div>

  <!-- ✅ Modal Popup -->
  <div
    v-if="isModalOpen"
    class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
  >
    <div class="bg-white p-6 rounded-3xl max-w-xl w-full shadow-lg relative">
      <h2 class="text-xl font-bold text-black tracking-tighter mt-8">
        How listings are verified
      </h2>
      <p class="mt-4 text-gray-900 tracking-tighter">
        Listings are verified after the Host submits photos or videos to show
        their place is where they say it is – and they have access to it.
      </p>
      <p class="mt-2 text-gray-900 tracking-tighter">
        In some cases, a listing can be verified if guest reviews confirm its
        location, if the Host provides extra documents or if the listing is
        managed by a company that signs an agreement.
      </p>
      <div class="mt-2 text-gray-900 tracking-tighter">
        This process has safeguards, but is not a guarantee that every detail on
        the listing is accurate.
        <NuxtLink to="/listing">
          <span class="underline text-base font-medium text-blue-600">
            Learn about listing verification
          </span>
        </NuxtLink>
      </div>

      <!-- Close Button -->
      <button
        @click="closeModal"
        class="absolute top-2 left-2 text-black hover:text-gray-600 text-xl p-2"
      >
        ✕
      </button>
    </div>
  </div>

  <div class="p-4 text-2xl font-semibold text-black mt-8">
    Neighbourhood highlights
    <p class="text-base font-normal text-black mt-4">
      The Colosseum is a towering monument of stone and history, standing as a
      testament to the courage and valor of those who have come before me. Its
      grandeur is humbling, its presence awe-inspiring. Each stone, stained with
      the sweat and blood of gladiators past, whispers tales of bravery and
      sacrifice.
    </p>
    <div
      class="py-4 lg:w-1/2 border-b border-black/20 mt-4 flex items-center gap-1"
    ></div>
  </div>

  <div class="flex flex-col justify-center items-center">
    <div
      class="w-[280px] h-[300px] relative overflow-hidden rounded-lg group mt-8"
    >
      <img :src="items[0]['gift']" class="w-full h-full object-cover" />
    </div>
    <div class="flex justify-center items-center text-center">
      <h2 class="text-lg font-normal text-black max-w-xl">
        Extraordinary experiences hosted by the world’s greatest names in music,
        film, TV, art, sports and more.
      </h2>
    </div>
  </div>
  <div
    class="py-4 lg:w-full border-b border-black/20 mt-4 flex items-center gap-1"
  ></div>
  <div class="px-2 mt-8">
    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 w-full mt-2">
      <!-- Block 1 -->
      <div class="flex items-start gap-2">
        <Mail class="w-10 text-black mt-1" />
        <div>
          <h2 class="text-lg font-medium text-black">Request to book</h2>
          <p class="text-wrap font-normal text-gray-600">
            Choose your dates, add your guests, then answer a question about why
            you want to go.
          </p>
        </div>
      </div>

      <!-- Block 2 -->
      <div class="flex items-start gap-2">
        <CircleCheck class="w-20 text-black mt-1" />
        <div>
          <h2 class="text-lg font-medium text-black">Selection process</h2>
          <p class="text-wrap font-normal text-gray-600">
            First, we’ll randomly choose a set of potential guests. Next, we’ll
            review their answers for unique perspectives and connections with
            the celebrity. Then, we’ll invite selected guests to book.
          </p>
        </div>
      </div>

      <!-- Block 3 -->
      <div class="flex items-start gap-2">
        <SquareUserRound class="w-20 text-black mt-1" />
        <div>
          <h2 class="text-lg font-medium text-black">Requirements</h2>
          <p class="text-wrap font-normal text-gray-600">
            You’ll need an active Airbnb account and the app to participate, and
            be a resident of an eligible country or region. It doesn’t cost
            anything to submit a request.
          </p>
        </div>
      </div>
    </div>
    <div
      class="py-4 lg:w-full border-b border-black/20 mt-4 flex items-center gap-1">
  </div>
    </div>
</template>
