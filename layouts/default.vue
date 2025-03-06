@import "tailwindcss";
@layer components {
.nave {my-auto; p-2; hover:bg-green-500; max-sm:w-full; max-sm:border-b-2; max-sm:border-black; max-sm:text-center;}
}

<template>
    <header class = "flex flex-row w-full max-sm:justify-between max-sm:relative">
        <div class = "basis-1/4 items-center justify-start px-4 min-w-40 max-sm:basis-auto">
            <img src="assets/images/logo.png" class="w-16 h-16">
        </div>
        <div class = "basis-1/4 max-sm:basis-auto">
        </div>
        <nav class = "basis-1/2 flex flex-row items-center justify-end px-4 gap-4 max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:bg-white max-sm:px-0">
            <NuxtLink to = "/" class="nave">Home</NuxtLink>
            <NuxtLink to = "/lab3" class="nave">Lab3</NuxtLink>
            <NuxtLink to = "/login" class="nave">LogIn</NuxtLink>
            <NuxtLink to = "/logout" class="nave">LogOut</NuxtLink>
        </nav>
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
<script setup>
import { useHead } from '#app';

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
</script>
