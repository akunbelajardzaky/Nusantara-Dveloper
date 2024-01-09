<!-- FAQComponent.vue -->

<template>
  <div class="mt-20">
    <h1 class="text-5xl font-bold mb-4">Frequently Asked Questions</h1>
    <p class="xl:w-1/2 xl:leading-7 mt-10">kami akan menjawab pertanyaan penting untuk kalian semua. dari sisi bagaimana Join di komunitas kami sampai menjadi tim utama</p>

    <div class="mt-10">
      <div v-for="(item, index) in faqItems" :key="index" class="mb-4">
        <div class="border border-gray-800 p-4 rounded-md transition-shadow hover:shadow-lg">
          <div class="flex items-start cursor-pointer" @click="toggleAnswer(index)">
            <div class="flex-shrink-0">
              <svg class="h-6 w-6 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
              </svg>
            </div>
            <div class="ml-3">
              <h3 class="text-lg font-medium text-gray-200">{{ item.question }}</h3>
              <transition name="fade">
                <p v-if="item.showAnswer" class="mt-2 text-gray-300">{{ item.answer }}</p>
              </transition>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      faqItems: [
        {
          question: "What is Vue.js?",
          answer: "Vue.js is a JavaScript framework for building user interfaces.",
          showAnswer: false,
        },
        {
          question: "How do I install Vue.js?",
          answer: "You can install Vue.js using npm or yarn. For example, npm install vue.",
          showAnswer: false,
        },
        // Add more FAQ items as needed
      ],
    };
  },
  methods: {
    toggleAnswer(index) {
      this.faqItems[index].showAnswer = !this.faqItems[index].showAnswer;
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
