<script setup>
import poor from '@/assets/img/poor.jpg'
</script>

<template>
    <body class="bg-white text-gray-800">
        <!-- Title Section -->
        <h1 class="font-bold text-3xl sm:text-5xl md:text-6xl py-8 px-6 sm:px-48">
            Striving to build Children’s future!
        </h1>
        <p class="font-light text-2xl sm:text-3xl px-6 sm:px-48">
            25 years of service for vulnerable children and young people!
        </p>

        <!-- Image Section -->
        <div class="px-6 sm:px-16 md:px-48 py-8">
            <img :src="poor" alt="Image description" class="w-full object-scale-down">
        </div>

        <!-- Buttons Section -->
        <div class="flex justify-center space-x-4 py-4">
            <a class="bg-green-500 duration-200 border-solid border-2 border-transparent rounded-md hover:border-green-500 hover:bg-white font-bold hover:text-green-500 px-6 py-3 text-center"
               href="https://www.chadet.org/images/chadet/content/annual%20report/Annual%20Report%202019.pdf" target="_blank">
                Download Annual Report
            </a>
            <a class="bg-red-600 duration-200 border-solid border-2 border-transparent rounded-md hover:border-red-500 hover:bg-white font-bold hover:text-red-500 text-white px-6 py-3 text-center"
               href="https://www.youtube.com/watch?v=z47AYd29XHE" target="_blank">
                Watch Video
            </a>
        </div>

        <!-- Information Section -->
        <div class="container px-4 sm:px-12 lg:px-48 py-8">
            <p class="py-10 px-6 sm:px-20 bg-green-200 rounded-md text-base sm:text-lg md:text-xl">
                CHADET is a prominent charitable organization in Ethiopia dedicated to promoting the welfare and protection of children facing challenging circumstances.
                Established during the height of the HIV/AIDS pandemic, CHADET focuses on educating communities about the epidemic's impact on children and families,
                fostering awareness and support. The organization initially launched its first project in the bustling Merkato area of Addis Ababa, a hub for street-connected and vulnerable children.
                Through training and deploying peer educators, CHADET effectively delivers crucial information and support to affected families, empowering them to navigate their challenges.
                Over the years, CHADET has expanded its reach, now operating in thirteen districts across the Amhara and Oromiya regions, as well as in Addis Ababa. The organization has developed five field offices
                and three service delivery centers, enhancing its capacity to address the needs of marginalized children. With a commitment to improving lives, CHADET continues to make significant strides in advocating for and supporting
                the most vulnerable populations in Ethiopia.
            </p>
        </div>
    </body>
</template>
