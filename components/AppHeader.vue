<script setup>

import { CircleUserRound, Search } from "lucide-vue-next"


</script>

<template>
  <div class=" z-50 bordr border-b bg-white p-6">
    <div class="max-w-5xl mx-auto flex items-center justify-between">
      
      <!-- Airbnb Logo -->
      <div class="flex items-center cursor-pointer">
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/6/69/Airbnb_Logo_Bélo.svg"
          alt="Airbnb Logo"
          class="h-8 w-auto"
        />
      </div>


      

      <!-- Search Bar -->
      <div
        class="flex  mx-32 border border-gray-300 rounded-full shadow-sm hover:shadow-md transition duration-300">
        <input   
          placeholder="Search here"
          class="flex-grow px-4 py-2 rounded-l-full focus:outline-none"/>
        <button
          class="bg-red-500 hover:bg-red-600 text-white rounded-full px-4 flex items-center justify-center">
          <Search class="w-5 h-5" />
        </button>
      </div>   
      <div class="flex items-center space-x-4 text-gray-700">
        <button
          class="hidden md:inline text-sm font-semibold hover:bg-gray-100 px-3 py-2 rounded-full transition"
        >
          Become a host
        </button>
        <button class="p-2 rounded-full hover:bg-gray-100">
          <CircleUserRound class="w-6 h-6" />
        </button>
      </div>
    </div>
    <div>
        <NuxtLink to="/">Home </NuxtLink>
                <NuxtLink to="/about">About </NuxtLink>

      </div>
  </div>
</template>
