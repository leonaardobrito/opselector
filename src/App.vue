<template>
  <div>

    <div class="max-w-sm rounded overflow-hidden justify-center shadow-lg py-8 h-[600px] content-between flex flex-wrap bg-neutral-700">
      <img class="w-full" src="https://random.imagecdn.app/500/250" alt="Sunset in the mountains">
      <div v-if="selected" class="px-6 py-4">
        Você comeu a
        <div class="font-bold text-xl mb-2">{{ selected['Devil Fruit'] }}</div>
        <div class="font-bold text-l mb-2">Parabéns!!!</div>
        <p class="text-slate-300 text-base py-5">
          Isso quer dizer que
          {{ selected['Character'] }} MORREU!
          
        </p>
        <p class="text-red-400 text-base py-5">
          
          Seu assassino!!!
        </p>
      </div>
      <div v-else  class="px-6 py-4">
       
        <div class="font-bold text-xl mb-2">Come a frutinha bem</div>
      </div>
      <button type="submit" @click="getAkuma()" id="btn" class="flex ">Comer fruta do djabo</button>
    </div>

    <!-- <div class="card">
      {{ selected['Devil Fruit'] }}
    </div> -->
  </div>
</template>

<script>
import { ref } from "vue";
import json from './data/akumas.json'

function randomIntFromInterval(min, max) { // min and max included 
  return Math.floor(Math.random() * (max - min + 1) + min)
}

let selected = ref("")
export default {

  methods: {
    getAkuma: () => {
      console.log(selected.value)
      const rndInt = randomIntFromInterval(1, 195)
      selected.value = json[rndInt];
      console.log(json[rndInt])
      return selected
    }
  },
  data() {
    return {
      selected
    }
  },
}
</script> -->

<style scoped>
#btn {
  background-color: rgb(173, 1, 1);
  font-weight: 600;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
