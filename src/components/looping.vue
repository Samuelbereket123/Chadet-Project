<script setup>
import one from '@/assets/img/01.png'
import two from '@/assets/img/02.jpg'
import three from '@/assets/img/03.jpg'
import four from '@/assets/img/04.png'
import five from '@/assets/img/05.jpg'
import six from '@/assets/img/06.jpg'
import seven from '@/assets/img/07.png'
import eight from '@/assets/img/08.png'
import nine from '@/assets/img/09.png'
import ten from '@/assets/img/10.png'
import eleven from '@/assets/img/11.jpg'
import tewlve from '@/assets/img/12.gif'
</script>

<template>
    <section>
        <!-- Header Section -->
        <div class="flex justify-center items-center py-10">
            <p class="text-4xl sm:text-6xl md:text-8xl font-bold">Our Supporters  </p>
        </div>

        <!-- Image Scrolling Section -->
        <div class="flex overflow-hidden group">
            <!-- First set of images -->
            <div class="flex animate-loop-scroll space-x-8 sm:space-x-12 md:space-x-16 w-auto">
                <img loading="lazy" :src="one" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="two" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="three" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="four" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="five" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="six" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="seven" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="eight" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="nine" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="ten" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="eleven" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="tewlve" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
            </div>
            
            <!-- Second set of images (for continuous scrolling effect) -->
            <div class="flex animate-loop-scroll space-x-8 sm:space-x-12 md:space-x-16 w-auto" aria-hidden="true">
                <img loading="lazy" :src="one" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="two" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="three" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="four" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="five" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="six" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="seven" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="eight" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="nine" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="ten" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="eleven" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
                <img loading="lazy" :src="tewlve" class="max-w-none w-16 sm:w-20 md:w-24 h-16 sm:h-20 md:h-24 object-contain" alt="">
            </div>
        </div>
    </section>
</template>
