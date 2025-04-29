<script setup>
import { ref, onMounted } from 'vue'

const currentIndex = ref(0)
const testimonials = [
  {
    name: 'Etenesh',
    date: '21 May 2016',
    content: "Etenesh faced hardship after her parents' divorce, living with her father and later moving to her mother. CHADET intervened, reuniting them, providing financial support, and helping her mother start a bakery. This enabled Etenesh to return to school without financial concerns, changing her life for the better.",
    rating: 5
  },
  {
    name: 'Tigist Tekele',
    date: '21 May 2016',
    content: "Tigist Tekele, after losing her parents, struggled to support her siblings. CHADET's training in food preparation, housekeeping, and childcare led to a job at a hotel in Addis Ababa, improving her family's situation. Tigist now dreams of further education, building a brighter future for herself and her family.",
    rating: 5
  },
  {
    name: 'Yemisrach Shimeles',
    date: '21 May 2016',
    content: "Yemisrach Shimeles, a single mother of two, struggled to provide for her family without education or skills. After joining CHADET's vocational training in auto body painting, she gained the skills and opportunity to pursue a career, giving her hope for a better future for herself and her children.",
    rating: 5
  }
]

const nextTestimonial = () => {
  currentIndex.value = (currentIndex.value + 1) % testimonials.length
}

const prevTestimonial = () => {
  currentIndex.value = (currentIndex.value - 1 + testimonials.length) % testimonials.length
}

onMounted(() => {
  const interval = setInterval(nextTestimonial, 5000)
  return () => clearInterval(interval)
})
</script>

<template>
  <section class="py-16 bg-gradient-to-b from-gray-50 to-white sm:py-20 lg:py-24">
    <div class="px-4 mx-auto max-w-7xl sm:px-6 lg:px-8">
      <div class="flex flex-col items-center">
        <div class="text-center max-w-2xl mx-auto">
          <h2 class="text-3xl font-bold text-gray-900 sm:text-4xl xl:text-5xl">
            Our Impact Stories
          </h2>
          <p class="mt-4 text-lg text-gray-600">
            Real stories of lives transformed through CHADET's initiatives
          </p>
        </div>

        <div class="mt-16 w-full">
          <div class="relative max-w-4xl mx-auto">
            <!-- Updated Gradient Background -->
            <div class="absolute -inset-x-2 inset-y-16 md:-inset-x-4 md:-inset-y-6">
              <div class="w-full h-full max-w-5xl mx-auto rounded-3xl opacity-20 blur-lg filter"
                style="background: linear-gradient(135deg, #22c55e 0%, #16a34a 50%, #15803d 100%)">
              </div>
            </div>

            <!-- Testimonial Card -->
            <div class="relative">
              <div class="overflow-hidden bg-white rounded-2xl shadow-xl">
                <div class="px-8 py-10 sm:px-12 sm:py-14">
                  <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-2">
                      <span v-for="i in testimonials[currentIndex].rating" :key="i"
                        class="text-yellow-400 transform transition-transform hover:scale-110">
                        ★
                      </span>
                    </div>
                    <div class="flex space-x-2">
                      <button @click="prevTestimonial"
                        class="p-2 text-gray-600 transition-colors hover:text-gray-900">
                        ←
                      </button>
                      <button @click="nextTestimonial"
                        class="p-2 text-gray-600 transition-colors hover:text-gray-900">
                        →
                      </button>
                    </div>
                  </div>

                  <blockquote class="mt-8">
                    <p class="text-xl leading-relaxed text-gray-900">
                      "{{ testimonials[currentIndex].content }}"
                    </p>
                  </blockquote>

                  <div class="flex items-center mt-8 border-t pt-4">
                    <div>
                      <p class="text-lg font-semibold text-gray-900">
                        {{ testimonials[currentIndex].name }}
                      </p>
                      <p class="mt-1 text-sm text-gray-600">
                        {{ testimonials[currentIndex].date }}
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="mt-8 text-center">
            <a href="https://chadet.org/what-we-do/case-stories.html" target="_blank"
              class="inline-flex items-center px-6 py-3 text-lg font-semibold text-white bg-green-600 rounded-lg transition-all duration-200 hover:bg-green-700 focus:ring-2 focus:ring-offset-2 focus:ring-green-500">
              View All Stories
              <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonial-enter-active,
.testimonial-leave-active {
  transition: all 0.5s ease;
}

.testimonial-enter-from {
  opacity: 0;
  transform: translateX(30px);
}

.testimonial-leave-to {
  opacity: 0;
  transform: translateX(-30px);
}
</style>