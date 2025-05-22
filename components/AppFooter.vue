<script setup>
import { Facebook, Instagram, Twitter } from 'lucide-vue-next'
</script>

<template>
  <div class="bg-gray-100 text-gray-800 border-t border-gray-300">
    <div
      class="max-w-full mx-auto px-6 py-6 grid grid-cols-2 sm:grid-cols-3 gap-8 text-sm"
    >
      <div>
        <h3 class="font-semibold mb-3">Support</h3>
        <ul class="space-y-2">
          <li><a href="#" class="hover:underline">Help Center</a></li>
          <li><a href="#" class="hover:underline">Get help with a safety issue</a></li>
          <li><a href="#" class="hover:underline">AirCover</a></li>
          <li><a href="#" class="hover:underline">Anti-discrimination</a></li>
          <li><a href="#" class="hover:underline">Disability support</a></li>
          <li><a href="#" class="hover:underline">Cancellation options</a></li>
          <li>
            <a href="#" class="hover:underline">Report neighborhood concern</a>
          </li>
        </ul>
      </div>
      <div>
        <h3 class="font-semibold mb-3">Hosting</h3>
        <ul class="space-y-2">
          <li><a href="#" class="hover:underline">Airbnb your home</a></li>
          <li><a href="#" class="hover:underline">AirCover for Hosts</a></li>
          <li><a href="#" class="hover:underline">Hosting resources</a></li>
          <li><a href="#" class="hover:underline">Community forum</a></li>
          <li><a href="#" class="hover:underline">Hosting responsibly</a></li>
          <li>
            <a href="#" class="hover:underline">Join a free Hosting class</a>
          </li>
          <li><a href="#" class="hover:underline">Find a co-host</a></li>
        </ul>
      </div>
      <div>
        <h3 class="font-semibold mb-3">Airbnb</h3>
        <ul class="space-y-2">
          <li><a href="#" class="hover:underline">2025 Summer Release</a></li>
          <li><a href="#" class="hover:underline">Newsroom</a></li>
          <li><a href="#" class="hover:underline">New features</a></li>
          <li><a href="#" class="hover:underline">Careers</a></li>
          <li><a href="#" class="hover:underline">INvestors</a></li>
          <li>
            <a href="#" class="hover:underline">Airbnb.org emergency stays</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="border-gray-300 px-6 py-6 text-sm">
      <div class="flex flex-col items-center sm:items-start gap-4">
        <!-- Language & Currency (side-by-side) -->
        <div class="flex items-center gap-6">
          <div class="flex items-center gap-1 hover:underline cursor-pointer">
            <span class="text-white">🌐</span>
            <span>English (IN)</span>
          </div>
          <div class="flex items-center gap-1 hover:underline cursor-pointer">
            <span>₹</span>
            <span>INR</span>
          </div>
        </div>
        <div class="flex flex-col sm:flex-row justify-between items-center sm:items-start gap-4 text-black w-full">
  <!-- Left: Footer Text -->
  <p class="text-sm text-center sm:text-left">
    &copy; 2025 Airbnb, Inc.
    <span class="hover:underline cursor-pointer"> · Privacy</span>
    <span class="hover:underline cursor-pointer"> · Terms</span>
    <span class="hover:underline cursor-pointer"> · Sitemap</span>
    <span class="hover:underline cursor-pointer"> · Company details</span>
  </p>

  <!-- Right: Social Icons -->
  <div class="flex gap-4 justify-end w-full sm:w-auto">
    <a href="https://facebook.com/AirbnbIndia" class="hover:text-blue-500">
      <Facebook class="w-4 h-4" />
    </a>
    <a href="https://instagram.com/airbnb" class="hover:text-pink-500">
      <Instagram class="w-4 h-4" />
    </a>
    <a href="https://x.com/airbnb_in" class="hover:text-black">
      <Twitter class="w-4 h-4" />
    </a>
  </div>
</div>

      </div>
      
    </div>
    
  </div>
</template>
