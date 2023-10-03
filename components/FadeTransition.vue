<template>
  <transition leave-active-class="duration-500 ease-in-out" enter-active-class="duration-500 ease-in-out"
    enter-to-class="opacity-100" leave-from-class="opacity-100" leave-to-class="opacity-0" enter-from-class="opacity-0">
    <slot />
  </transition>
</template>
