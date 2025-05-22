<script setup>
import { Bookmark } from "lucide-vue-next";
import { Dot } from "lucide-vue-next";
import { ref, onMounted, onBeforeUnmount } from "vue";

const locationVerificationPoints = [
  "We do not require the location of most listings to be verified.",
  "We may not detect fraud or efforts to circumvent or bypass the verification process.",
  "Verification does not consider any safety or quality issues in the listing or in the surrounding neighborhood.",
  "The Verified Location badge status of a listing could change without notice.",
];

const showButton = ref(false);

function scrollToTop() {
  window.scrollTo({
    top:0,
    behaviour:"smooth",
  });
}
function handleScroll(){
   showButton.value = window.scrollY > 200;
}
onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});
onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});

</script>

<template>
  <div class="px-4 py-8 lg:w-1/2">
    <h1 class="p-2 text-3xl font-semibold mb-5">
      How listing locations are verified
    </h1>
    <p class="px-4 -mt-4 text-lg font-normal tracking-tighter text-gray-900">
      You shouldn’t have to worry that a listing is fake or isn’t where it says
      it is. That’s why we have the location verification program so that hosts
      can demonstrate that a listing on Airbnb is a real home, at an accurate
      location, and that they have access to that location. While we encourage
      all hosts to verify the location of their listings, for most hosts and
      listings, location verification is optional.
    </p>
    <p class="px-4 py-4 text-lg font-norma tracking-tighter text-gray-900">
      When you see the Verified Location badge on the map, this means that the
      listing has satisfied the verification requirements described in this
      article. In some cases, existing listings that meet specific criteria may
      receive a Verified Location badge based on historical data or other
      information, as described below.
    </p>
    <p class="px-4 py-4 text-lg font-normal tracking-tighter text-gray-900">
      All references to “location verification,” “verifying a listing’s
      location,” or “verified locations” mean the listing has satisfied the
      verification requirements described in this article. Our location
      verification process helps to confirm only that the listing is real and at
      an accurate location—but location verification is optional for most
      listings, and we don’t verify the host’s listing description or any other
      details they provide about their listing as part of this process. Location
      verification has safeguards, but is not a guarantee that a listing is what
      the host claims it to be. For more information on the process of
      verification, including the various methods used and the limitations of
      the process, please see below.
    </p>
    <div class="p-8 pt-2 w-full">
      <p class="text-base font-medium text-gray-700">In this article</p>
    </div>
    <div class="px-8 w-full">
      <div class="underline flex items-start gap-2 -mt-8">
        <Bookmark class="w-4 h-5 text-black fill-black mt-1" />
        <a
          href="#process"
          class="text-base font-medium underline text-black hover:text-black"
        >
          How the process works
        </a>
      </div>
      <div class=" flex items-start gap-2 mt-2">
        <Bookmark class="w-4 h-5 text-black fill-black mt-1" />
        <a href="#special-situations" class="text-base font-medium underline">
          Special situations
        </a>
      </div>
      <div class="underline flex items-start gap-2 mt-2">
        <Bookmark class="w-4 h-5 text-black fill-black mt-1" />
        <a href="#location" class="text-base font-medium underline">
          Limitations of location verification
        </a>
      </div>
      <div
        class="py-4 w-full border-b border-black/25 mt-4 flex items-center gap-1"
      ></div>
    </div>
    <div id="process" class="p-4 text-2xl font-semibold">
      How the process works
      <p class="text-base font-normal mt-4">
        There are two primary methods that may be used to verify a listing’s
        location:
      </p>
    </div>
    <div class="px-4 py-14 flex items-start justify-center gap-4 -mt-8">
      <span  class="w-3 h-2  rounded-full bg-black -mt-2"></span>
      <!-- <h3 class="text-lg font-semibold -mt-6">Photos:</h3> -->
      <p class="text-base font-normal -mt-5">
        <span class="text-lg font-semibold -mt-6 mr-4">Photos:</span> Hosts are
        asked to take 2 new photos outside and inside of their listing using the
        Airbnb app with precise location sharing enabled. The inside photo must
        match a photo of the same area from the host’s listing details page.
      </p>
    </div>
    <div class="px-4  flex items-start justify-center gap-4 -mt-8">
      <Dot class="w-[15px] h-[6px] rounded-full bg-black -mt-2" />
      <p class="text-base font-normal -mt-5">
        <span class="text-lg font-semibold -mt-6 mr-4">Videos:</span> Hosts are
        asked to record short videos demonstrating that they are at specific
        locations in and around the listing—inside near the front door, outside
        showing the exterior view, and a nearby street sign.
      </p>
    </div>
    <div id="special-situations" class="p-4 text-2xl font-semibold">
      Special situations
      <p class="text-base font-normal mt-2">
        Some listings that satisfy additional criteria or provide supplemental
        information to us in another way may have earned a Verified Location
        badge without requiring the host to complete the verification processes
        described above. The hosts of these Listings may have provided the
        supplemental documentation or information to us during the listing
        creation process, in connection with a verification process, or we may
        rely on previously collected information like guest feedback or ratings
        and reviews.
      </p>
    </div>
    <div id="location" class="p-4 text-2xl font-semibold">
      Limitations of location verification
      <p class="text-base font-normal mt-2 leading-2                  ">
        Guests should have confidence that the listing they’ve chosen to book is
        a real home with an accurate location that the host has access to.
        That’s why we have a process in place to allow hosts to verify the
        location of listings they publish on Airbnb.
      </p>
      <p class="text-base font-normal mt-6">
        Even with safeguards, no verification process is foolproof and we cannot
        guarantee a listing’s location or that the host has access to it. Some
        limitations of our verification process include:
      </p>
    </div>

    <div class="p-4 -mt-8">
      <ul class="list-disc list-inside text-black text-base space-y-2">
        <li v-for="(point, index) in locationVerificationPoints" :key="index">
          {{ point }}
        </li>
      </ul>
      <div>
        <div class="py-8 flex items-start justify-center gap-2 -mt-6">
          <Dot class="w-[20px] h-[6px] rounded-full bg-black mt-2 " />
          <p class="text-base font-normal ">
          <span class="text-base font-normal "
            >Only the information requested as part of the location verification
            method we’ve asked the host to complete is verified. No other
            information a host publishes on their listing is verified as part of
            this program, such as
            <span class="text-base font-bold">Listing details </span>or
            <span class="text-base font-bold">
              Neighborhood highlights.</span
            ></span
          >
          </p>
        </div>
      </div>
    </div>

    <div class="p-4 flex items-start -mt-8">
      <span class="text-base font-normal">
        you still need assistance with your host or listing,
        <span class="underline text-base font-semibold text-black"
          >contact us </span
        >for support.</span
      >
    </div>
    <div class="p-4 mt-4">
      <span class="text-lg font-medium"
        >Did this article help?
        <span class="inline-flex gap-4 ml-2">
          <span
            class="underline text-base font-normal text-black cursor-pointer"
            >Yes</span
          >
          <span
            class="underline text-base font-normal text-black cursor-pointer"
            >No</span
          >
        </span>
      </span>
    </div>
    <div
        class="py-4 lg:w-1/2 border-b border-black/25 mb-4 flex items-center gap-1"
      ></div>
      <div class="p-4 text-xl font-semibold">Need to get in touch?
        <p class="text-base font-normal mt-4">We’ll start with some questions and get you to the right place.</p>
      </div>
      <div class="px-4 py-8 flex -mt-10 cursor-pointer text-base font-semibold tracking-tighter w-1/2">
        <h1 class=" py-2 px-4 rounded-xl border border-gray-800">
          Contact us
        </h1>
      </div>
      <div class=" px-4 py-4 -mt-12 ">
        <span class="inline-flex gap-1">You can also
          <span class="underline text-base font-medium cursor-pointer">give us feedback.</span>
        </span> 
        
      </div>
      <div>
    

    <!-- Back to Top button -->
    <button
      v-show="showButton"
      @click="scrollToTop"
      class="fixed bottom-8 right-8 bg-blue-600 text-white w-10 h-10 rounded-full shadow-lg hover:bg-blue-700 transition-opacity duration-300"
      aria-label="Back to Top"
    >
      ↑
    </button>
  </div>
  </div>
</template>
