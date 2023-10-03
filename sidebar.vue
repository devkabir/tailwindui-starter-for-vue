<template>
  <button type="button" @click.prevent="openSlideOver" :class="`fixed ${toggleClass}`">
    <slot name="toggleIcon" />
  </button>

  <div class="relative z-[999999]" v-show="slideOverRoot">
    <FadeTransition name="bg-fade">
      <div class="fixed inset-0 opacity-80" v-if="slideOver"></div>
    </FadeTransition>
    <div class="fixed inset-0 overflow-hidden">
      <div class="absolute inset-0 overflow-hidden">
        <div class="fixed inset-y-0 right-0 flex max-w-full pl-10 pointer-events-none">
          <SlideTransition name="slide-over">
            <div class="w-screen max-w-md pointer-events-auto" v-if="slideOver">
              <div class="flex flex-col h-full bg-white divide-y divide-gray-200 shadow-xl">
                <div class="flex flex-col flex-1 min-h-0 py-6 overflow-y-scroll">
                  <div class="px-4 sm:px-6">
                    <div class="flex items-start justify-between">
                      <h2 class="text-lg font-medium text-gray-900" id="slide-over-title">{{ title }}</h2>
                      <div class="flex items-center ml-3 h-7">
                        <button type="button" @click="closeSlideOver"
                          class="text-gray-400 bg-white rounded-md hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500">
                          <span class="sr-only">Close panel</span>
                          <XMarkIcon class="w-6 h-6 " aria-hidden="true" />
                        </button>
                      </div>
                    </div>
                  </div>
                  <div class="relative flex-1 px-4 mt-6 sm:px-6">
                    <slot name="content" />
                  </div>
                </div>
                <div class="flex justify-end flex-shrink-0 px-4 py-4">
                  <slot name="footer" />
                </div>
              </div>
            </div>
          </SlideTransition>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import FadeTransition from "@/components/transitions/FadeTransition.vue";
import SlideTransition from "@/components/transitions/SlideTransition.vue";
import { PaintBrushIcon, XMarkIcon } from "@heroicons/vue/24/outline";
import { ref } from "vue";

defineProps({
  toggleClass: {
    type: String,
    default: "p-2 z-[99999] text-white bg-indigo-600 rounded-md bottom-4 left-1/2 right-1/2 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 cursor-pointer",
  },
  title: {
    type: String,
    default: "Slide Over Title",
  }
})

const slideOver = ref<Boolean>(true);
const slideOverRoot = ref<Boolean>(true);

const openSlideOver = () => {
  slideOverRoot.value = true;
  slideOver.value = true;
}

const closeSlideOver = () => {
  slideOver.value = false;
  setTimeout(() => {
    slideOverRoot.value = false;
  }, 800);
}
</script>
