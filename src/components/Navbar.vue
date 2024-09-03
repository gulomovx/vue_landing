<template>
      <nav class="sticky top-0 z-50 py-3 backdrop-blur-lg border- shadow-md border-neutral-700/80">
            <div class="container px-4 mx-auto relative text-sm">
                  <div class="flex justify-between items-center">
                        <div class="flex-shrink-0 flex items-center  ">
                              <h1 class="md:text-[29px] text-[18px] font-medium">TechSight</h1>
                        </div>
                        <ul v-for="item in navItems" class="hidden lg:flex gap-2 space-x-12">
                              <li key="item">
                                    <a :href="item.href">{{ item.label }}</a>
                              </li>
                        </ul>
                        <!-- buttons -->
                        <div class="hidden lg:flex justify-center space-x-12 items-center">
                              <a href="#" class="py-2 px-3 border rounded-md">Sign In</a>
                              <a href=""
                                    class="bg-gradient-to-r from-orange-500 to-orange-800 text-white py-2 px-3 rounded-md">
                                    Create account
                              </a>


                        </div>
                        <!-- toggle menu icons -->
                        <div class="lg:hidden md:flex flex-col justify-end">
                              <button @click="toggleMenu" class="">
                                    <span v-if="!isOpen" class="">
                                          <Menu />
                                    </span>
                                    <span v-else>
                                          <X />
                                    </span>
                                    <!-- {{ isOpen ? <X/> : <Menu/> }} -->
                              </button>
                        </div>

                  </div>
                  <!-- mobile menu -->
                  <div v-if="isOpen"
                        class="fixed  right-0 z-20 bg-neutral-600 w-full p-12 flex flex-col justify-center items-center gap-4 lg:hidden">
                        <!-- <X/>       -->
                        <ul v-for="item in navItems">
                              <li class="text-white" :key="item">
                                    <a :href="item.href">{{ item.label }}</a>
                              </li>
                        </ul>
                        <!-- buttons -->
                        <div class="flex flex-col items-center  mx-auto gap-y-4 justify-center space-x-6">
                              <a href="#" class="py-2 px-3 border  rounded-md text-white">Sign In</a>
                              <a href=""
                                    class="bg-gradient-to-r from-orange-500 to-orange-800 text-white py-2 px-3 rounded-md">
                                    Create account
                              </a>
                        </div>
                  </div>
            </div>

      </nav>
</template>
<script setup>
import { navItems } from './index'
import { Menu, X } from 'lucide-vue-next'
import { ref } from 'vue';

const isOpen = ref(false)
const toggleMenu = () => {
      isOpen.value = !isOpen.value
}

</script>