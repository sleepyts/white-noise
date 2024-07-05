<script setup>
import {onMounted} from "vue";
import NoisePlayer from "./components/noisePlayer.vue";

const testObj = {
  name: "鸟",
  fileName: "../../public/audio/birds.mp3",
}

const noises = [
  {
    name: "鸟",
    fileName: "../../public/audio/birds.mp3",
  },
  {
    name: "小溪",
    fileName: "../../public/audio/brook.mp3",
  },

  {
    name: "秋风",
    fileName: "../../public/audio/autumn.mp3",
  },
  {
    name: "潮汐",
    fileName: "../../public/audio/tide.mp3",
  },
  {
    name: "夏夜",
    fileName: "../../public/audio/summer.mp3",
  },
  {
    name: "风铃",
    fileName: "../../public/audio/wind-chime.mp3",
  },
  {
    name: "篝火",
    fileName: "../../public/audio/bonfire.mp3",
  },
  {
    name: "大雨",
    fileName: "../../public/audio/rain.mp3",
  },

]
</script>

<template>
  <div v-for="noise in noises" :key="noise.name">
    <noise-player :noise="noise"></noise-player>
  </div>
</template>

<style scoped>

</style>
