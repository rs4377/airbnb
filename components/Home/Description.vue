<script setup>
import {WandSparkles,Clock,Heart,PawPrint,ShieldCheck,} from "lucide-vue-next";
import { ref } from "vue";

const show = ref(false);

const experiencePoints = [
  "The patron will meet you at the Colosseum after sunset and lead you inside. Whether you emerge from this night victor or vanquished, know this: your eyes will embrace a sight not oft seen. The memory of the Colosseum aglimmer in candlelight will be yours.",
  "Descend into the hypogeum, the underground chambers where gladiators prepare for battle. There, you will don armor that most closely reflects your gladiator type, whether that be murmillo, thraex, provocator, retiarius, or contrarete. Choose wisely.",
  "Traverse the torch-lit, labyrinthine bowels of the Colosseum where Maximus and countless other warriors walked before you. Reflect on their fate, and yours, as you trace their historic steps.",
  "Savor the symphony of swords and shields as seasoned gladiators engage in a thrilling showdown for your benefit. You must study them, for your turn will soon follow.",
  "Enjoy a spread of victuals like grapes, pomegranates, almonds, and walnuts. You’re a gladiator, not an emperor. You cannot afford to be gluttonous. Overindulgence will dull your senses and slow your reflexes.",
  "Train in the art of gladiator combat and test your mettle as you face off against your fellow warriors. A summa rudis—your referee—will ultimately determine your fate. May you taste the sweetness of glory with infestus pollex and join the ranks of victorious gladiators since time immemorial.",
];

const images = ["/images/host-profile.png"];

const items = [
  {
    id: 1,
    "image-nine": "/images/image-nine.png",
  },
];

const showCard = ref(false);
const isModalOpen = ref(false);

function openModal() {
  console.log("Opening modal...");
  isModalOpen.value = true;
}

function closeModal() {
  console.log("Closing modal...");
  isModalOpen.value = false;
}
</script>

<template>
  <div class="px-1 md:px-4 w-full lg:w-1/2 relative text-justify">
    <!-- Introduction -->
    <p class="text-base text-black mt-8">
      Hail! So, you wish to step into the role of a gladiator? This path is not
      for the faint of heart. However, if you believe you possess the courage,
      let us open the gates of Rome’s legendary Colosseum to test the limits of
      your strength and honor. There, under the dark of night, we will determine
      who was born for victory and who for defeat. Will you answer the call of
      destiny in the world’s most famous battleground or languish in cowardice?
    </p>

    <h2 class="text-lg font-semibold text-black mt-4">What you'll do</h2>
    <p class="text-base text-black mt-2">
      You will feel the adrenaline rush, the sand between your fingers, and the
      weight of your armor. You will hear the echoes of gladiators past in the
      Colosseum’s catacombs and the unmistakable clank of steel in its arena.
      You will see the moon’s reflection off the travertine stone through the
      sweat dripping down your face. You will become a gladiator.
    </p>
    <p class="text-base text-black mt-4">
      A wealthy patron has graciously volunteered to escort you through what
      very well may be the most defining moment of your life. And, as we all
      know, what we do in life echoes in eternity.
    </p>

    <!-- Experience Highlights -->
    <div class="mt-6">
      <ul class="list-disc list-inside text-black text-base space-y-2">
        <li v-for="(point, index) in experiencePoints" :key="index">
          {{ point }}
        </li>
      </ul>
    </div>

    <!-- Notes -->
    <div class="text-base font-medium text-black mt-4">
      Other things to note
    </div>
    <p class="text-base text-black mt-2">
      The Colosseum is a place of combat, not of rest. By decree of the Emperor,
      no guest shall stay the night.
    </p>
    <p class="text-base text-black mt-4">
      **See Gladiator II, only in cinemas**.
    </p>

    <!-- Registration -->
    <h1 class="text-base font-medium text-black py-2">Registration number</h1>
    <div class="bg-white border-b border-black/20 flex items-center">
      <p class="text-base text-black mb-8">Exempt</p>
    </div>

    <!-- Host -->
    <div id="meet-your-host" class="text-lg font-bold text-black mt-16">
      Meet your host
    </div>
    <div class="w-full flex justify-center px-8">
      <div class="h-[350px] flex items-center justify-center">
        <NuxtLink to="/lucius">
        <div
        
          class="relative w-[335px] md:w-96 h-72 bg-white border border-gray-200 rounded-3xl shadow-xl flex flex-col items-center justify-center"
        >
          <img
            :src="images[0]"
            alt="Host Image"
            class="w-32 h-32 rounded-full object-cover mb-2"
          />
          <div class="mb-2 text-pink-600">
            <ShieldCheck
              class="absolute bottom-[40%] right-[25%] w-20 h-10 fill-white"
            />
          </div>
          <h2 class="text-base font-bold text-black">Lucius</h2>
          <p class="text-base font-normal text-gray-600">
            Started hosting in 2024
          </p>
          
        </div>
        </NuxtLink>
        </div>
        </div>
        
      
    </div>

    <!-- Fun Facts -->
    <div class="flex items-start gap-4 mt-2">
      <WandSparkles class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">Most useless skill: Quoting Virgil</p>
    </div>
    <div class="flex items-start gap-4 mt-2">
      <Clock class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">
        I spend too much time: training, but it's never enough
      </p>
    </div>
    <div class="flex items-start gap-4 mt-2">
      <Heart class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">I'm obsessed with: Contemplating fate</p>
    </div>
    <div class="flex items-start gap-4 mt-2">
      <PawPrint class="w-5 h-5 text-black mt-1" />
      <p class="text-base text-black">I fought a rhinoceros once</p>
    </div>

    <!-- Host Description -->
    <p class="mt-8">
      ‘Tis I, Lucius. I did not choose this path, but the rage in my heart calls
      me to the arena. I do not fight for the roar of the crowd or the glory of
      victory. No, my battles are personal. I fight to defend my family and
      honor to ensure the future of Rome is free from tyranny. I am not merely
      entertainment for the masses, I am a guardian, a defender, a gladiator.
    </p>

    <div class="py-4 border-b border-black/20 mt-4"></div>

    <!-- Accessibility Features -->
    <div class="flex items-start gap-4 mt-16">
      <h2 class="text-base font-semibold text-black">Accessibility features</h2>
    </div>
    <p class="text-gray-700 font-normal">
      This info was provided by the Host and reviewed by Airbnb.
    </p>

    <div
      class="w-[200px] h-[150px] relative overflow-hidden rounded-lg group mt-8"
    >
      <img
        :src="items[0]['image-nine']"
        class="w-full h-full object-cover rounded-2xl"
      />
    </div>

    <h2 class="text-lg font-semibold text-black mt-4 w-1/2">
      Guest entrance and parking
    </h2>
    <p class="text-gray-500 font-medium">Step-free access</p>

    <!-- Show More Button -->
    <div class="flex mt-6 w-1/2">
      <button
        @click="openModal"
        class="md:w-1/2 py-2 px-3 rounded-2xl border border-gray-800 hover:scale-110 transition-transform"
      >
        Show all details
      </button>
    </div>

    <!-- Modal -->
    <div
      v-if="isModalOpen"
      class="fixed inset-0 max-w-9xl mx-auto bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div
        class="bg-white p-6 w-full h-full shadow-lg relative overflow-y-auto"
      >
        <button
          @click="closeModal"
          class="absolute top-4 left-4 text-black text-3xl"
        >
          ←
        </button>

        <h2 class="text-3xl w-full lg:w-1/3 font-semibold text-black mt-16 px-4">
          Accessibility features
        </h2>
        <p class="text-base w-full lg:w-1/3 text-gray-900 mt-2 px-4">
          This info was provided by the Host and reviewed by Airbnb.
        </p>

        <div class="flex flex-col lg:flex-row md:flex-cols items-center">
        <div class="mt-0 px-4 w-full lg:w-1/3 text-base font-normal text-black">Guest entrance and parking
          <h3 class="text-xl font-semibold text-gray-900">Step-free access</h3>
          <p class="text-sm font-normal mt-2">
            There are no steps, stairs or curbs on the entire path from a
            guest's arrival to the listing entrance. For some listings like
            apartments, this includes all exterior pathways, hallways, elevators
            or anything else a guest will encounter on the way to the home. Any
            door thresholds or pathway obstacles must be less than 2 inches (5
            cm) high.
          </p>
        </div>
        <div class="mt-6 w-full lg:w-1/2 md:w-full   h-[350px] px-4">
          <img
            :src="items[0]['image-nine']"
      
            class=" rounded-2xl"
          />
          
        </div>
        </div>

        
      </div>
      <div class="py-4 border-b border-black/20 mt-4">
    </div>

    </div>
  
</template>
