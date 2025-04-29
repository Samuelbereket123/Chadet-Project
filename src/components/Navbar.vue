<script setup>
import logo from '@/assets/img/chadet.png'
import { ref, onMounted, computed, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)
const activeSection = ref('Home')
const headerRef = ref(null)

const menuItems = [
  { name: 'Home', href: '#home' },
  { name: 'Who we are', href: '#about' },
  { name: 'What we do', href: '#services' },
  { name: 'Calender', href: '#calendar' },
  { name: 'Courses', href: '#courses' }
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
  if (window.scrollY > 100) isMobileMenuOpen.value = false
}

const handleResize = () => {
  if (window.innerWidth > 1024) isMobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', handleResize)
})
</script>

<template>
  <header ref="headerRef" 
          :class="[
            'fixed w-full transition-all duration-500 z-50',
            isScrolled ? 'bg-green-500/90 backdrop-blur-md shadow-lg text-white' : 'bg-transparent text-black',
            isScrolled ? 'py-2' : 'py-3'
          ]">
    <nav class="container mx-auto px-4 flex items-center justify-between">
      <!-- Logo -->
      <div class="relative z-50">
        <a href="#" class="group block relative overflow-hidden rounded-xl">
          <img :src="logo" 
               alt="Chadet Logo" 
               class="transform transition-all duration-500 will-change-transform"
               :class="[
                 isScrolled ? 'h-10' : 'h-12',
                 'w-auto'
               ]">
          <div class="absolute inset-0 bg-gradient-to-tr from-white/20 via-white/10 to-transparent opacity-0 group-hover:opacity-100 transition-all duration-500"></div>
        </a>
      </div>

      <!-- Desktop Navigation -->
      <ul class="hidden lg:flex items-center gap-1">
        <li v-for="item in menuItems" 
            :key="item.name" 
            class="relative">
          <a :href="item.href"
             @click="activeSection = item.name"
             class="group px-4 py-2 rounded-lg relative overflow-hidden flex items-center"
             :class="[
               activeSection === item.name ? 'bg-green-800 text-white' : '',
               isScrolled ? 'text-base hover:text-white' : 'text-sm hover:text-green-800',
             ]">
            <!-- Hover Background Effect -->
            <div class="absolute inset-0 w-full h-full bg-green-500/10 transform origin-left -translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-out"></div>
            
            <span class="relative z-10 font-medium tracking-wide whitespace-nowrap transform transition-all duration-300">
              {{ item.name }}
            </span>

            <div class="absolute bottom-0 left-0 w-full h-0.5 bg-green-800 transform scale-x-0 group-hover:scale-x-100 transition-transform duration-500 ease-out"></div>
          </a>
        </li>
      </ul>

      <!-- Mobile Menu Button -->
      <button @click="isMobileMenuOpen = !isMobileMenuOpen"
              class="lg:hidden relative z-50 p-2 rounded-lg hover:bg-green-600/30 focus:outline-none focus:ring-2 focus:ring-green-500/50 transition-all duration-300"
              :class="[isScrolled ? '' : 'scale-90']"
              :aria-expanded="isMobileMenuOpen"
              aria-label="Toggle menu">
        <div class="w-6 h-6 flex flex-col justify-around">
          <span class="block h-0.5 w-full transform transition-all duration-300"
                :class="[
                  isMobileMenuOpen ? 'rotate-45 translate-y-2.5 bg-white' : '',
                  isScrolled ? 'bg-white' : 'bg-black'
                ]"></span>
          <span class="block h-0.5 w-full transform transition-all duration-300"
                :class="[
                  isMobileMenuOpen ? 'opacity-0' : 'opacity-100',
                  isScrolled ? 'bg-white' : 'bg-black'
                ]"></span>
          <span class="block h-0.5 w-full transform transition-all duration-300"
                :class="[
                  isMobileMenuOpen ? '-rotate-45 -translate-y-2.5 bg-white' : '',
                  isScrolled ? 'bg-white' : 'bg-black'
                ]"></span>
        </div>
      </button>

      <!-- Mobile Menu Overlay -->
      <div v-show="isMobileMenuOpen" 
           class="lg:hidden fixed inset-0 bg-green-900/90 backdrop-blur-md z-40"
           @click="isMobileMenuOpen = false">
        <div class="h-full flex flex-col items-center justify-center space-y-8 p-4"
             @click.stop>
          <a v-for="item in menuItems"
             :key="item.name"
             :href="item.href"
             class="text-2xl font-medium text-white hover:text-green-200 transform hover:scale-110 transition-all duration-300"
             @click="isMobileMenuOpen = false">
            {{ item.name }}
          </a>
        </div>
      </div>
    </nav>
  </header>

  <!-- Spacer for content -->
  <div :class="['h-16', isScrolled ? 'h-14' : 'h-16']"></div>
</template>

<style scoped>
.backdrop-blur-md {
  backdrop-filter: blur(12px);
}

/* Prevent body scroll when mobile menu is open */
:global(body) {
  @apply overflow-x-hidden;
}
:global(body.menu-open) {
  @apply overflow-hidden;
}
</style>