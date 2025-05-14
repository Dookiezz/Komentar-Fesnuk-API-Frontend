<template>
  <div class="hero bg-base-200 min-h-screen px-4 py-10">
    <div class="hero-content w-full max-w-6xl grid grid-cols-1 lg:grid-cols-2 gap-12">
      <!-- KIRI -->
      <div class="space-y-6">
        <div class="badge badge-primary whitespace-normal text-sm px-4 py-2">
          #random-generated-comment&nbsp;#AbsurdHumor
        </div>

        <h1 class="text-4xl sm:text-5xl font-bold">Absurd Comment API</h1>

        <p class="text-base text-gray-600">
          Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda excepturi
          exercitationem quasi. In deleniti eaque aut repudiandae et a id nisi.
        </p>

        <div class="flex flex-col space-y-2">
          <div class="avatar-group -space-x-4">
            <div class="avatar">
              <div class="w-10">
                <img src="https://img.daisyui.com/images/profile/demo/yellingcat@192.webp" />
              </div>
            </div>
            <div class="avatar">
              <div class="w-10">
                <img src="https://img.daisyui.com/images/profile/demo/yellingcat@192.webp" />
              </div>
            </div>
            <div class="avatar">
              <div class="w-10">
                <img src="https://img.daisyui.com/images/profile/demo/yellingcat@192.webp" />
              </div>
            </div>
            <div class="avatar">
              <div class="w-10">
                <img src="https://img.daisyui.com/images/profile/demo/yellingcat@192.webp" />
              </div>
            </div>
            <div class="avatar avatar-placeholder">
              <div class="bg-neutral text-neutral-content w-12">
                <span>+69</span>
              </div>
            </div>
          </div>
          <p class="text-sm text-gray-500">69 orang telah menggunakan ini</p>
        </div>
      </div>

      <!-- KANAN -->
      <div class="flex flex-col items-start gap-4 w-full">
        <button class="btn btn-primary w-full sm:w-auto" @click="generateText">
          Get random text now
        </button>

        <textarea
          ref="outputText"
          v-model="randomText"
          placeholder="Random text will appear here..."
          class="textarea textarea-primary w-full h-32"
        ></textarea>

        <button class="btn btn-outline btn-sm" @click="copyToClipboard">Copy to clipboard</button>

        <p v-if="copied" class="text-green-500 text-sm">✅ Copied!</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Random text content
const randomText = ref("");

// Simulate fetch / generate
function generateText() {
  const samples = [
    "Omke gass omke gass!",
    "Apakah di Eropa ada Indomaret?",
    "Pernahkah kamu bermimpi jadi pisang?",
    "Ini absurd tapi efektif.",
    "Kucing bisa coding sekarang.",
  ];
  const index = Math.floor(Math.random() * samples.length);
  randomText.value = samples[index];
}

// Copy to clipboard
const outputText = ref(null);
const copied = ref(false);

function copyToClipboard() {
  if (outputText.value) {
    navigator.clipboard.writeText(randomText.value);
    copied.value = true;
    setTimeout(() => {
      copied.value = false;
    }, 2000);
  }
}
</script>
