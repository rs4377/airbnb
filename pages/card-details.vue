<script setup>
import { ref } from 'vue'
import { GalleryHorizontal } from "lucide-vue-next";
import {Share} from "lucide-vue-next";
import {Heart} from "lucide-vue-next"

import Description from "@/components/Home/Description.vue";
import Hostinfo from "@/components/Home/Hostinfo.vue";
import Map from "@/components/Home/Map.vue";
import Rules from '~/components/Home/Rules.vue';

const isModelOPen = ref(false) 

const images = [
  "/images/image-one.png",
  "/images/image-two.png",
  "/images/image-three.png",
  "/images/image-four.png",
  "/images/image-five.png",
  "/images/image-six.png",
  "/images/image-seven.png",
  "/images/image-eight.png",
  "/images/image-nine.png",
  "/images/image-ten.png",
]

const openModel = () => {
  isModelOPen.value = true
}

const closeModel = () => {
  isModelOPen.value = false
}
</script>


<template>
  <div class="max-w-6xl  mx-auto p-2">
    <!--heading -->
    <div
      class="p-4 bg-white  mt-4 flex justify-between items-center flex-wrap ">
      <h1 class="text-xl font-bold mt-2 text-black">
        Train for Gladiator II glory glory
      </h1>
      <div class="flex">
      <button
      
    @click="shareContent"
    class="underline text-black hover:bg-gray-100 rounded-2xl flex items-center gap-2 font-medium px-3 "
  >
  <Share class="w-4 h-4"/>
    Share
  </button>
  <button
  @click="saveContent"
  class="underline text-black hover:bg-gray-100 rounded-2xl flex items-center gap-1 font-medium px-3 "
  >
  <Heart class="w-4 h-4"/> 
  Save
   
  </button>
    </div>
    </div>
    <!-- Two-column image layout -->
    <div class="flex flex-row gap-1 w-full px-1">
      <!-- First Large Image -->
      <div class="w-full md:w-1/2 h-[350px] relative group overflow-hidden rounded-xl">
        <img
          :src="images[0]" class="w-full h-full object-cover"/>
        
        <div 
          class="absolute inset-0 bg-black bg-opacity-30 opacity-0 group-hover:opacity-100 transition duration-200">
      </div>
      </div>

      <!-- Four Smaller Images -->
      <div class="w-full md:w-1/2 sm:1/2 grid grid-cols-2 gap-1 h-[350px]">
        <div
          v-for="(image, index) in images.slice(1, 5)"
          :key="index"
          class="relative group overflow-hidden rounded-xl">
          <img
            :src="image" class="w-full h-full object-cover"
          />
          <div
            class="absolute inset-0 bg-black bg-opacity-30 opacity-0 group-hover:opacity-100 transition duration-300">
        </div>

          <!-- Show All Photos Button -->
          <button
            v-if="index === 3"
            @click="openModel"
            class="absolute bottom-3 right-3 z-20 bg-white text-black text-sm font-medium px-3 py-1 rounded-lg shadow-md hover:bg-gray-100 transition flex items-center gap-1">
            <GalleryHorizontal class="w-5 h-5" />
            Show all photos
          </button>
        </div>
      </div>
    </div>
    <!--MOdel-->
    <div 
    v-if="isModelOPen"
    class="fixed inset-0 bg-black bg-opacity-60 flex justify-center items-center z-50">
    <div class="bg-white p-6 rounded-xl max-w-5xl w-full overflow-y-auto max-h-[90vh] relative">
        <button
          @click="closeModel"

          class="absolute top-3 right-3 bg-black text-white px-3 py-1 rounded-lg hover:bg-gray-800">
           Close
        </button>
        <h2 class="text-xl font-semibold mb-4 text-black">All Photos</h2>
        <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
          <img
            v-for="(img, idx) in images"
            :key="idx"
            :src="img"
            class="w-full h-48 object-cover rounded-lg"
          />
        </div>
        </div>
    </div> 
  <Hostinfo/>
  <Description/>
  <Map/>
  <Rules/>
  </div>
</template>
