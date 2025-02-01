<script setup>
import logo from '@/assets/img/chadet.png'
</script>

<template>
    <header class="bg-green-500 text-white">
        <nav class="container py-5 px-4 flex flex-col gap-4 items-center sm:flex-row">
            <div class="flex items-center gap-x-4">
                <div class="flex">
                    <a href="#" class="text-white font-bold text-3xl"><img :src="logo" alt=""></a>
                   <!-- <h1 class="text-5xl py-4 px-3 font-bold text-green-200">CHADET</h1> -->

                </div>                
            </div>
            <ul class="flex flex-1 justify-end gap-x-10">
                <router-link class="cursor-pointer  bg-green-800 duration-200 border-solid border-2 border-transparent rounded-md hover:border-green-500 hover:bg-white font-bold hover:text-green-500 text-white px-6 py-3 text-center" :to="{name:''}">Home</router-link>
                <router-link class= "cursor-pointer  bg-green-800 duration-200 border-solid border-2 border-transparent rounded-md hover:border-green-500 hover:bg-white font-bold hover:text-green-500 text-white px-6 py-3 text-center" :to="{name:''}">Who we are</router-link>
                <router-link class="cursor-pointer  hover:bg-green-800 hover:rounded-none" :to="{name:''}">What we do</router-link>
                <router-link class="cursor-pointer  hover:bg-green-800 hover:rounded-none" :to="{name:''}">Calender</router-link>
                <router-link class="cursor-pointer  hover:bg-green-800 hover:rounded-none" :to="{name:''}">Courses</router-link>
                <!--<li class="cursor-pointer  hover:bg-green-800 hover:rounded-none">Courses</li> -->
            </ul>
        </nav>
    </header>

</template>

