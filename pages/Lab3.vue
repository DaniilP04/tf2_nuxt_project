<template>
    <main class="flex-col flex-grow">
      <div class="flex flex-row items-center w-full text-center justify-between  max-sm:grid max-sm:grid-rows-2 max-sm:grid-cols-5">
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Scout" v-model="selectedpic">
          <img :src="scout.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
         :class="{'border-rose-500': selectedpic === 'Scout'}">Scout</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Soldier" v-model="selectedpic">
          <img :src="soldier.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Soldier'}">Soldier</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Pyro" v-model="selectedpic">
          <img :src="pyro.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Pyro'}">Pyro</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Demoman" v-model="selectedpic">
          <img :src="demoman.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Demoman'}">Demoman</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Heavy" v-model="selectedpic">
          <img :src="heavy.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Heavy'}">Heavy</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Engineer" v-model="selectedpic">
          <img :src="engineer.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Engineer'}">Engineer</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Medic" v-model="selectedpic">
          <img :src="medic.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Medic'}">Medic</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Sniper" v-model="selectedpic">
          <img :src="sniper.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Sniper'}">Sniper</label>
        <label><input @click="playmusic" class = "hidden mx-2" type="radio" value="Spy" v-model="selectedpic">
          <img :src="spy.image" class="w-20 h-20 border-2 rounded-[100px] hover:border-rose-400" 
          :class="{'border-rose-500': selectedpic === 'Spy'}">Spy</label>
  
      </div>
      <div class="flex justify-center items-center flex-grow">
        <div class="blockcap" v-if="selectedpic == 'Scout'">
          <img :src="scout.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ scout.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Soldier'">
          <img :src="soldier.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ soldier.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Pyro'">
          <img :src="pyro.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ pyro.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Demoman'">
          <img :src="demoman.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ demoman.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Heavy'">
          <img :src="heavy.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ heavy.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Engineer'">
          <img :src="engineer.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ engineer.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Medic'">
          <img :src="medic.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ medic.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Sniper'">
          <img :src="sniper.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ sniper.name }}</p> -->
        </div>
        <div class="blockcap" v-if="selectedpic == 'Spy'">
          <img :src="spy.gif" class ="w-60 h-68 pt-2">
          <!-- <p class = "text-black text-xl">{{ spy.name }}</p> -->
        </div>
      </div>
    
    </main>
  </template>
  
  <script setup lang="ts">
  
  import { reactive } from 'vue'
  import demomanimg from '/assets/img/demoman.png'
  import engineerimg from '/assets/img/engineer.png'
  import heavyimg from '/assets/img/heavy.png'
  import medicimg from '/assets/img/medic.png'
  import pyroimg from '/assets/img/pyro.png'
  import scoutimg from '/assets/img/scout.png'
  import sniperimg from '/assets/img/sniper.png'
  import soldierimg from '/assets/img/soldier.png'
  import spyimg from '/assets/img/spy.png'
  import demomangif from '/assets/img/demoman.gif'
  import engineergif from '/assets/img/engineer.gif'
  import heavygif from '/assets/img/heavy.gif'
  import medicgif from '/assets/img/medic.gif'
  import pyrogif from '/assets/img/pyro.gif'
  import scoutgif from '/assets/img/scout.gif'
  import snipergif from '/assets/img/sniper.gif'
  import soldiergif from '/assets/img/soldier.gif'
  import spygif from '/assets/img/spy.gif'
  import music from '/assets/music/class_select.mp3'
import { errorMessages } from 'vue/compiler-sfc'
  
  
  interface tf2classes{
    name: string,
    image: string,
    gif: string
  }
  const scout = reactive<tf2classes>({
    name: "scout",
    image: scoutimg,
    gif: scoutgif
  });
  
  const soldier = reactive<tf2classes>({
    name: "soldier",
    image: soldierimg,
    gif: soldiergif
  });
  
  const pyro = reactive<tf2classes>({
    name: "pyro",
    image: pyroimg,
    gif: pyrogif
  });
  
  const demoman = reactive<tf2classes>({
    name: "demoman",
    image: demomanimg,
    gif: demomangif
  });
  
  const heavy = reactive<tf2classes>({
    name: "heavy",
    image: heavyimg,
    gif: heavygif
  });
  
  const engineer = reactive<tf2classes>({
    name: "engineer",
    image: engineerimg,
    gif: engineergif
  });
  
  const medic = reactive<tf2classes>({
    name: "medic",
    image: medicimg,
    gif: medicgif
  });
  
  const sniper = reactive<tf2classes>({
    name: "sniper",
    image: sniperimg,
    gif: snipergif
  });
  
  const spy = reactive<tf2classes>({
    name: "spy",
    image: spyimg,
    gif: spygif
  });
  
  
  const selectedpic = ref<string>('')
    const audio_player = ref<HTMLAudioElement | null>(null);

  onMounted(() => {
  audio_player.value = new Audio(music);
});
onUnmounted(() => {
  if (audio_player.value) {
    audio_player.value.pause();
    audio_player.value = null;
  }
});

  const playmusic = ()  => {
    if (audio_player.value && audio_player.value.paused) {
      audio_player.value.play().catch(error => console.error("error of playing music: ", error))
    }
  }
  </script>
  
  <style scoped>
  .blockcap {
    @apply left-0 w-full h-auto flex items-center justify-center bg-transparent;
  }
  
  .blockcap img {
    @apply w-auto h-[75vh] max-sm:h-[55vh] object-contain;
  }

  </style>