<script setup>
import { ShieldCheck } from "lucide-vue-next";
import { WandSparkles, Clock, Heart, PawPrint } from "lucide-vue-next";
import { Flag } from "lucide-vue-next";

const images = ["/images/host-profile.png"];
const items = [{ id: 1, "image-one": "/images/image-one.png" }];

const isModalOpen = ref(false);
const reportSuccess = ref(false);

function openModal() {
  console.log("Opening modal");
  isModalOpen.value = true;
}

function closeModal() {
  console.log("Closing modal");
  isModalOpen.value = false;
}

function handleReport() {
  closeModal();
  reportSuccess.value = true;

  setTimeout(() => {
    reportSuccess.value = false;
  }, 3000);
}

const isLuciusOpen = ref(false);

function openLucius() {
  console.log("Opening lucius");
  isLuciusOpen.value = true;
}

function closeLucius() {
  console.log("Closing lucius");
  isLuciusOpen.value = false;
}
</script>
<template>
  <div class="px-4 py-4 border-t border-black/10"></div>
  <div class="w-full px-8">
    <div class="h-[350px]">
      <div
        class="relative w-[335px] md:w-96 h-72 bg-white border border-gray-200 rounded-3xl shadow-xl flex flex-col items-center justify-center"
      >
        <img
          :src="images[0]"
          alt="Host Image"
          class="w-32 h-32 rounded-full object-cover mb-2"
        />
        <!-- ShieldCheck Icon -->
        <div class="mb-2 text-pink-600">
          <ShieldCheck
            class="absolute bottom-[38%] right-[28%] w-10 h-9 fill-white"
          />
          <div class="text-xl font-semibold text-black">Lucius Host</div>
        </div>
      </div>
    </div>
    <div class="flex items-start gap-4 mt-2">
      <WandSparkles class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">Most useless skill: Quoting Virgil</p>
    </div>
    <div class="flex items-start gap-4 mt-4">
      <Clock class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">
        I spend too much time: training, but it's never enough
      </p>
    </div>
    <div class="flex items-start gap-4 mt-4">
      <Heart class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">I'm obsessed with: Contemplating fate</p>
    </div>
    <div class="flex items-start gap-4 mt-4">
      <PawPrint class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">I fought a rhinoceros once</p>
    </div>
    <div class="flex items-start gap-4 mt-4">
      <ShieldCheck class="w-5 h-5 text-black mt-1" />

      <button @click="openLucius" class="underline font-bold cursor-pointer">
        Identity verified
      </button>
      <div
        v-if="isLuciusOpen"
        class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
      >
        <div
          class="bg-gradient-to-br from-[#2e0f0f] to-[#1a1a1a] p-6 w-[75%] md:w-[500px] h-auto max-h-[90%] rounded-2xl shadow-2xl relative overflow-y-auto text-white"
        >
          <button
            @click="closeLucius"
            class="absolute top-4 left-4 text-white text-3xl hover:text-red-500 transition"
          >
            ✕
          </button>

          <transition name=" fade-slide" appear>
            <div
              class="relative mt-8 bg-gradient-to-br  from-[#2e2e2e] via-[#1f1f1f] to-black rounded-2xl shadow-2xl p-6 w-[500px] h-[400px] sm:w-full md:w-full transition-all duration-300 ease-in-out hover:scale-105 border border-yellow-500/30 overflow-hidden"
            >
              <h2
                class="text-3xl font-extrabold text-center text-yellow-400  tracking-wider"
              >
                Lucius
              </h2>
              <p class="text-lg font-normal text-center text-yellow-300 ">
                Verified since June 2024
              </p>

              <!-- Decorative shapes repeated all over background -->
              <div
                class="absolute inset-0 flex flex-wrap p-2 pointer-events-none select-none"
                style="opacity: 0.15"
              >
                <template v-for="n in 80" :key="n">
                  <span
                    class="text-blue-300 text-3xl m-1 w-[8%]"
                    :style="{ transform: `rotate(${(n * 5) % 360}deg)` }"
                  >
                    {{ ["❥", "❧", "♡", "❦", "✦", "❁"][n % 6] }}
                  </span>
                </template>
              </div>

              <!-- Content above shapes -->
              <img
                src="/images/host-profile.png"
                alt="Lucius Image"
                class="relative w-24 h-24 rounded-full mx-auto mb-2 border-4 border-violet-700 object-cover shadow-lg z-10"
              />
              <h3
                class="relative text-xl font-bold text-center text-yellow-400 z-10"
              >
                Lucius Veritas
              </h3>
              <p
                class="relative text-gray-300 text-center mt-2 text-sm italic z-10"
              >
                Verified Gladiator | Rome Defender
              </p>
              <div
                class="relative mt-4 text-center text-sm text-yellow-200 font-medium italic z-10"
              >
                “Steel sharpens steel. Fate sharpens me.”
              </div>
              <p class="text-base font-light text-yellow-400 w-1/2 mt-4">
                Trust is the cornerstone of Airbnb’s community, and identity
                verification is part of how we build it.
              </p>
            </div>
          </transition>
          <p class="p-2">Our identity verification process checks a person’s information against trusted third-party sources or a government ID. The process has safeguards but doesn’t guarantee that someone is who they say they are.
            <span class="underline font-semibold text-blue-600 cursor-pointer">Learn more</span> </p>
        </div>
      </div>
    </div>

    <p class="mt-8">
      ‘Tis I, Lucius. I did not choose this path, but the rage in my heart calls
      me to the arena. I do not fight for the roar of the crowd or the glory of
      victory. No, my battles are personal. I fight to defend my family and
      honor to ensure the future of Rome is free from tyranny. I am not merely
      entertainment for the masses, I am a guardian, a defender, a gladiator.
    </p>
    <div class="px-4 py-4 border-b border-black/10"></div>
    <div class="py-8 text-2xl font-medium">Lucius’s listings</div>
    <router-link to="/card-details">
      <div
        class="w-[200px] h-[150px] relative overflow-hidden rounded-lg group"
      >
        <img
          :src="items[0]['image-one']"
          class="w-full h-full object-cover rounded-2xl"
        />
      </div>
    </router-link>
    <div class="text-sm font-medium py-2">
      Home
      <p class="text-sm font-normal text-gray-600">
        Train for Gladiator II glory
      </p>
    </div>
    <div class="px-4 py-4 border-b border-black/10"></div>

    <div class="flex items-start gap-4 mt-4 mb-16 transition">
      <Flag class="w-5 h-5 text-black mt-1" />
      <button
        @click="openModal"
        class="text-base font-medium text-black hover transition"
      >
        Report Lucius
      </button>
    </div>

    <div
      v-if="isModalOpen"
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div
        class="bg-white p-6 w-[90%] md:w-[500px] h-auto max-h-[80%] rounded-xl shadow-lg relative overflow-y-auto"
      >
        <button
          @click="closeModal"
          class="absolute top-4 left-4 text-black text-3xl"
        >
          ✕
        </button>
        <h2 class="text-3xl w-full lg:w-1/3 font-medium text-black p-8">
          What’s happening?
        </h2>
        <p class="text-lg font-normal px-8 -mt-7 mb-4">
          This will only be shared with Airbnb.
        </p>
        <div class="px-8 space-y-4">
          <label class="flex items-center gap-3 cursor-pointer">
            <input
              type="radio"
              name="reportReason"
              class="form-radio text-black h-4 w-4"
            />
            <span class="text-base font-normal"
              >I think they’re scamming or spamming me</span
            >
          </label>
          <div class="border-b border-black/10"></div>

          <label class="flex items-center gap-3 cursor-pointer">
            <input
              type="radio"
              name="reportReason"
              class="form-radio text-black h-4 w-4"
            />
            <span class="text-base font-normal">They’re being offensive</span>
          </label>
          <div class="border-b border-black/10"></div>

          <label class="flex items-center gap-3 cursor-pointer">
            <input
              type="radio"
              name="reportReason"
              class="text-black h-4 w-4"
            />
            <span class="text-base font-normal">Something else</span>
          </label>
          <div class="border-b border-black/10"></div>
        </div>

        <div class="flex justify-end px-8 mt-6">
          <button
            @click="handleReport"
            class="px-10 py-4 bg-black text-white text-sm font-semibold rounded-lg hover:bg-gray-800 transition"
          >
            Ok
          </button>
        </div>
      </div>
    </div>
    <!-- Success Message -->
    <div
      v-if="reportSuccess"
      class="fixed bottom-6 right-6 bg-green-500 text-white px-4 py-3 rounded-lg"
    >
      ✅ Report sent successfully!
    </div>
  </div>
</template>
