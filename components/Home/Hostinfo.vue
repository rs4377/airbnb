<script setup>
import { ShoppingCart } from "lucide-vue-next";
import { SquarePen } from "lucide-vue-next";
import { Sparkles } from "lucide-vue-next";
import { Clapperboard } from "lucide-vue-next";
import { Trophy } from "lucide-vue-next";
</script>

<template>
   <div class="px-4  bg-white mt-4 flex relative group items-center overflow-hidden text-justify justify-between ">
      <div>
        <h1 class="text-lg font-semibold text-black">Rome, Italy</h1>
        <h2 class="text-base text-gray-600">Evening Experience</h2>
      </div>
      <button
        class="px-6 py-4 bg-black text-white text-sm font-medium rounded-lg hover:bg-gray-800 transition flex items-center gap-2">
        <ShoppingCart class="w-5 h-5" />
        Buy Now
      </button>
    </div>  
     <!-- Host Info -->
     <div>
    <div
      class="p-4 py-4 lg:w-1/2 bg-white border-t border-b border-black/20 mt-4 flex items-center gap-4">
      <a href="#meet-your-host">
      <img
        src="/images/host-profile.png"
        alt="Host Profile"
        class="w-12 h-12 rounded-full object-cover border border-red-600 bg-gray-200"/>
      </a>
        <div class="flex flex-col">
        <h1 class="text-lg font-semibold text-black">Hosted by Lucius</h1>
        <h2 class="text-base text-gray-600">Gladiator</h2>
      </div>
    </div>

    <!-- Experience Description Sections -->
    <div class="px-4 lg:w-1/2">
      <div class="flex items-start gap-4 mt-4">
        <SquarePen class="w-5 h-5 text-black mt-1" />
        <div>
          <h2 class="text-lg font-medium text-black">
            Behold the Colosseum's grandeur
          </h2>
          <h3 class="text-wrap font-light text-gray-700">
            Its doors are forever closed at night...except for this night.
          </h3>
        </div>
      </div>

      <div class="flex items-start gap-4 mt-4">
        <Sparkles class="w-5 h-5 text-black mt-1" />
        <div>
          <h2 class="text-lg font-medium text-black">
            Adorn yourself in armour
          </h2>
          <h3 class="text-wrap font-light text-gray-700">
            Select your gear carefully - it must align with your fighting
            technique
          </h3>
        </div>
      </div>

      <div class="flex items-start gap-4 mt-4">
        <Clapperboard class="w-5 h-5 text-black mt-1" />
        <div>
          <h2 class="text-lg font-medium text-black">
            Observe as gladiators collide
          </h2>
          <h3 class="text-wrap font-light text-gray-700">
            Contemplate your mortality as my brethren duel before you. Study
            them well.
          </h3>
        </div>
      </div>

      <div class="flex items-start gap-4 mt-4">
        <Trophy class="w-5 h-5 text-black mt-1" />
        <div>   
          <h2 class="text-lg font-medium text-black">
            Fulfil your gladiator destiny
          </h2>
          <h3 class="text-wrap font-light text-gray-700">
            Hone your fighting skills and battle amongst your own rank.
          </h3>
        </div>
      </div>
    </div>
    <div
      class="py-4 lg:w-1/2 border-b border-black/20 mt-4 flex items-center gap-1"></div>
    </div>
</template>