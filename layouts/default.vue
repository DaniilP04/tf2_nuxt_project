<template>
    <header class = "flex flex-row w-full bg-rose-400 max-sm:justify-between relative   ">
        <div class="basis-1/4 items-center justify-start px-4 min-w-40 max-sm:basis-auto">
            <img src="assets/images/tf2-laugh.gif" class="w-16 h-16">
        </div>
        <div class="basis-1/4 ma-sm:basis-auto"></div>
        <nav :class="{'basis-1/2 flex flex-row items-center justify-end px-4 gap-4':!burger || burger,  
        'max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:bg-rose-400 max-sm::px-0':burger, 'max-sm:hidden': !burger}">
            <NuxtLink to="/" class = "headbtn max-sm:w-20 max-sm:border-b-2 max-sm:text-center">Home</NuxtLink>
            <div class = "my-auto p-2 rounded-2xl border-2 max-sm:w-20 max-sm:border-b-2 max-sm:text-center" @click = "switch_submenu">Labs
                <div class ="flex flex-col absolute top-full bg-rose-450 text-white w-56 text-center max-sm:relative max-sm:w-full max-sm:bg-rose-450" v-show = "submenu">
                    <NuxtLink to="/Lab3" class = "headbtn max-sm:w-100 max-sm:border-b-2 max-sm:text-center">Lab3</NuxtLink>
                    <NuxtLink to="/Lab4" class = "headbtn max-sm:w-full max-sm:border-b-2 max-sm:text-center">Lab4</NuxtLink>
                    <NuxtLink to="/Lab5" class = "headbtn max-sm:w-full max-sm:border-b-2 max-sm:text-center">Lab5</NuxtLink>
                    <NuxtLink to="/Lab6" class = "headbtn max-sm:w-full max-sm:border-b-2 max-sm:text-center">Lab6</NuxtLink>
                </div>
            </div>
            <NuxtLink to="/login" class = "headbtn max-sm:w-20 max-sm:border-b-2 max-sm:text-center">LogIn</NuxtLink>
            <NuxtLink to="/logout" class = "headbtn max-sm:w-20 max-sm:border-b-2 max-sm:text-center">LogOut</NuxtLink>
        </nav>
        <div v-if="!burger" @click = "switch_burger" class = "max-sm:flex max-sm:flex-col max-sm:mr-8 max-sm:mt-4 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6">
            <span class = "h-[3px] w-full bg-black"></span>
            <span class = "h-[3px] w-full bg-black"></span>
            <span class = "h-[3px] w-full bg-black"></span>
        </div>
        <div v-else class = "max-sm:flex max-sm:flex-col max-sm:mr-8 max-sm:mt-4 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6" @click="switch_burger">
            <span class = "h-[3px] w-full bg-black rotate-[45deg] relative top-[9px]"></span>
            <span class = "h-[3px] w-full bg-black opacity-0"></span>
            <span class = "h-[3px] w-full bg-black relative rotate-[-45deg] bottom-3"></span>
        </div>
    </header>
    
    <main class="p-5 flex bg-rose-300 h-screen">
        <slot />
    </main>

    <footer class = "flex flex-row w-full bg-rose-400 border-t-2 border-rose-400 items-center justify-center p-4 gap-12">
        <a href= ""><img src="assets/images/icons8-steam-50.png" class="w-12 h-12"></a>
        <a href= ""><img src="assets/images/icons8-youtube-50.png" class="w-12 h-12"></a>
        <a href= ""><img src="assets/images/icons8-tik-tok-50.png" class="w-12 h-12 bg-transparent"></a>
    </footer>
</template> 

<script setup lang="ts">
import {ref} from 'vue'
useHead({   
    script: [
        {
            async:true, 
            src: 'https://www.googletagmanager.com/gtag/js?id=G-F94EC6QJCD',
        },
        {
            innerHTML: `
            window.dataLayer = window.dataLayer || [];
            function gtag(){dataLayer.push(arguments);}
            gtag('js',new Date());
            gtag('config', 'G-F94EC6QJCD');
            `,
            type: 'text/javascript',
        },
    ],
    __dangerouslyDisableSanitizersByTagID: {
        gtag: ['innerHTML'],
    },
});

const burger = ref<Boolean>(false)
const submenu = ref<Boolean>(false)

const switch_burger = ()=> {burger.value = !burger.value}
const switch_submenu = ()=> {submenu.value = !submenu.value}

</script>
