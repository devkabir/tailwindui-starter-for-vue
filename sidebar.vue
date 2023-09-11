<template>
  <div class="relative z-[999999]" aria-labelledby="slide-over-title" role="dialog" aria-modal="true">
    <transition leave-active-class="ease-in-out duration-500" enter-active-class="ease-in-out duration-500"
                enter-to-class="opacity-100" leave-from-class="opacity-100" leave-to-class="opacity-0" enter-from-class="opacity-0">
      <div class="fixed inset-0 transition-opacity bg-gray-500 bg-opacity-75" v-if="toggle"></div>
    </transition>
    <transition leave-active-class="transform transition ease-in-out duration-500 sm:duration-700" enter-active-class="transform transition ease-in-out duration-500 sm:duration-700"
                enter-to-class="translate-x-0" leave-from-class="translate-x-0" leave-to-class="translate-x-full" enter-from-class="translate-x-full">
      <div class="fixed inset-y-0 right-0 flex max-w-full pl-10 pointer-events-none" v-if="toggle">
        <div class="w-screen max-w-md pointer-events-auto">
          <div class="flex flex-col h-full py-6 overflow-y-scroll bg-white shadow-xl">
            <div class="px-4 sm:px-6">
              <div class="flex items-start justify-between">
                <h2 class="text-lg font-medium text-gray-900" id="slide-over-title">Panel title</h2>
                <div class="flex items-center ml-3 h-7">
                  <button type="button"
                          @click="closeToggle"
                          class="text-gray-400 bg-white rounded-md hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                    <span class="sr-only">Close panel</span>
                    <!-- Heroicon name: outline/x-mark -->
                    <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                         stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                      <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"/>
                    </svg>
                  </button>
                </div>
              </div>
            </div>
            <div class="relative flex-1 px-4 mt-6 sm:px-6">
              <!-- Replace with your content -->
              <div class="absolute inset-0 px-4 sm:px-6">
                <div class="h-full border-2 border-gray-200 border-dashed" aria-hidden="true"></div>
              </div>
              <!-- /End replace -->
            </div>
          </div>
        </div>
      </div>
    </transition>


  </div>


</template>

<script setup>
import {storeToRefs} from "pinia";
import {useSlideOver} from "@/stores/slide-over";


const {toggle} = storeToRefs(useSlideOver())
const {closeToggle} = useSlideOver()
</script>
