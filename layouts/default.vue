<template>
    <header class = "flex flex-row w-full max-sm:justify-between max-sm:relative">
        <div class = "basis-1/4 items-center justify-start px-4 min-w-40 max-sm:basis-auto">
            <img src="assets/images/logo.png" class="w-16 h-16">
        </div>
        <div class = "basis-1/4 max-sm:basis-auto">
        </div>
        <nav class="{'basis-1/2 flex flex-row items-center justify-end px-8 gap-4': !burger || burger, 'max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:bg-white max-sm:px-0': burger, 'max-sm:hidden': !burger}">
            <NuxtLink to = "/" class="my-auto p-2 hover: bg-gray-500 rounded-lg max-sm:border-b-2 max-sm:w-full max-sm:border-black max-sm:text-center">Home</NuxtLink>
            <div class="my-auto p-2 hover: bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center max-sm:px-0 max-sm:pb-0" @click = "switch_submenu">Labs
                <div class="flex flex-col top-2 absolute bg-white text-black w- text-center max-sm:relative max-sm:w-full max-sm:bg-red-100 max-sm:px-0" v-show="submenu">
                    <NuxtLink to =/lab3 class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab3</NuxtLink>
                    <NuxtLink to =/lab4 class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab4</NuxtLink>
                    <NuxtLink to =/lab5 class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab5</NuxtLink>
                    <NuxtLink to =/lab6 class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab6</NuxtLink>
                </div>
            </div>
            <NuxtLink to = "/login" class="{'my auto p-2 hover:bg-gray-500 rounded-lg max-sm:border-b-2 max-sm:w-full max-sm:border-black max-sm:text-center': submenu,'my-auto p-2 hover-bg-gray-500 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:text-center':!submenu}">Login</NuxtLink>
            <NuxtLink to = "/logout" class="my auto p-2 hover:bg-gray-500 rounded-lg max-sm:border-b-2 max-sm:w-full max-sm:border-black max-sm:text-center">Logout</NuxtLink>
        </nav>
        <div v-if = "!burger" @click = "switch_burger" class = "max-sm:flex-col max-sm:flex max-sm:mr-8 max-sm:justify-between max-sm:items-center max-sm:w8 max-sm:h8">
            <span class="h-[3px] w-full bg-green-200"></span>
            <span class="h-[3px] w-full bg-green-200"></span>
            <span class="h-[3px] w-full bg-green-200"></span>
        </div>
        <div v-else class = "max-sm:flex-col max-sm:flex max-sm:mr-8 max-sm:justify-between max-sm:items-center max-sm:w8 max-sm:h6" @click="switch_burger">
            <span class="h-[3px] w-full bg-green-200 rotate-45 relative top[9px]"></span>
            <span class="h-[3px] w-full bg-green-200 opacity-0"></span>
            <span class="h-[3px] w-full bg-green-200 relative bottom-3 rotate-[-45deg]"></span>
        </div>
        </header>
    
    <main class = "p-5 flex bg-green-100 h-screen">
        <slot />
    </main>

    <footer class = "flex flex-row w-full bg-green-300 border-t-2 border-gray-400 items-center justify-center px-4 py-2 gap-4">
        <a href = "https://www.youtube.com/"><img src = "assets/images/youtube.svg" class = "w-16 h-16"></a>
        <a href = "https://www.github.com/"><img src = "assets/images/github.svg" class = "w-16 h-16"></a>
        <a href = "https://www.facebook.com/"><img src = "assets/images/facebook.svg" class = "w-16 h-16"></a>
    </footer>
</template>

<!-- Google tag (gtag.js) -->

<script setup lang="ts">
import {useHead} from '#app';
import {ref} from 'vue';

useHead({
    script: [
    {
        async: true,
        src: "https://www.googletagmanager.com/gtag/js?id=G-WS7NZ26B7F"
    },
    {
        innerHTML: `
            window.dataLayer = window.dataLayer || [];
            function gtag(){dataLayer.push(arguments);}
            gtag('js', new Date());
            gtag('config', 'G-WS7NZ26B7F');
        `,
        type: "text/javascript",
    },
    ],
    __dangerouslyDisableSanitizersByTagID: {
        gtag: ["G-WS7NZ26B7F"]
    },
});

const burger = ref<boolean>(false)
const submenu = ref<boolean>(false)
const switch_burger = ()=>{burger.value = !burger.value}
const switch_submenu = ()=>{submenu.value = !submenu.value}

</script>
