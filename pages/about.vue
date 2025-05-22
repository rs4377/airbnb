<script setup>
import { ref } from "vue";
import { Heart } from "lucide-vue-next";
import { ChevronRight } from "lucide-vue-next";

const dummyData = [
  {
    id: 1,
    title: "Train of Gladiator II",
    description: "Hosted by Lucius",
    price: "37,800",
    images: [
      "/images/image-one.png",
      "/images/image-two.png",
      "/images/image-three.png",
      "/images/image-seven.png"
    ],
  },
  {
    id: 2,
    title: "Train of Gladiator III",
    description: "Hosted by Maximus",
    price: "42,500",
    images: [
      "/images/image-four.png",
      "/images/image-five.png",
      "/images/image-six.png",
    ],
  },
];

const currentImageIndexes = ref({});

onMounted(() => {
  dummyData.forEach((item) => {
    currentImageIndexes.value[item.id] = 0;
  });
});

const nextImage = (postId, imagesLength) => {
  const current = currentImageIndexes.value[postId];
  currentImageIndexes.value[postId] = (current + 1) % imagesLength;
};

const prevImage = (postId, imagesLength) => {
  const current = currentImageIndexes.value[postId];
  currentImageIndexes.value[postId] =
    (current - 1 + imagesLength) % imagesLength;
};

const likedPost = ref({});

const toggleLike = (postId) => {
  likedPost.value[postId] = !likedPost.value[postId];
};
</script>

<template>
  <div class="p-4">
   

    

    <h2 class="text-xl font-semibold mb-4">Homes</h2>

    <div class="grid grid-cols-1 md:grid-cols-4 gap-5">
      <div
        v-for="(item, index) in dummyData"
        :key="index"
        class="w-[250px] flex-shrink-0"
      >
        <NuxtLink to="/card-details">
          <div
            class="w-[350px] h-[300px] relative overflow-hidden rounded-lg group"
          >
            <!-- Heart Icon -->
            <div
              class="absolute top-2 right-2 z-10 shadow-md cursor-pointer hover:scale-105 transition-transform"
              @click.prevent="toggleLike(item.id)"
            >
              <Heart
                :class="['w-10 h-10 transition-all duration-300 text-white']"
                :fill="likedPost[item.id] ? '#FF0000' : 'none'"
                :stroke="likedPost[item.id] ? '#FF6F60' : 'currentColor'"
              />
            </div>

            <!-- Image Slider -->
            <img
              :src="item.images[currentImageIndexes[item.id]]"
              alt="image"
              class="w-full h-full object-cover rounded-xl transition duration-300"
            />

            <!-- Prev Arrow -->
            <button
              @click.prevent="prevImage(item.id, item.images.length)"
              class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-white text-black p-2 rounded-full shadow"
            >
              ‹
            </button>

            <!-- Next Arrow -->
            <button
              @click.prevent="nextImage(item.id, item.images.length)"
              class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-white text-black p-2 rounded-full shadow"
            >
              ›
            </button>
          </div>

          <!-- Info Section -->
          <div class="mt-2 relative flex justify-between w-full">
            <div class="flex flex-col">
              <h1 class="font-medium text-base">{{ item.title }}</h1>
              <p class="text-sm">{{ item.description }}</p>
              <p class="font-medium underline underline-offset-2">
                {{ item.price }}
              </p>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>
