<script setup>
import {onMounted} from "vue";
import { Analytics } from "@vercel/analytics/react"
import NoisePlayer from "./components/noisePlayer.vue";

const testObj = {
  name: "鸟",
  fileName: "audio/birds.mp3",
}

const noises = [
  {
    name: "鸟",
    fileName: "/audio/birds.mp3",
  },
  {
    name: "小溪",
    fileName: "/audio/brook.mp3",
  },

  {
    name: "秋风",
    fileName: "/audio/autumn.mp3",
  },
  {
    name: "潮汐",
    fileName: "/audio/tide.mp3",
  },
  {
    name: "夏夜",
    fileName: "/audio/summer.mp3",
  },
  {
    name: "风铃",
    fileName: "/audio/wind-chime.mp3",
  },
  {
    name: "篝火",
    fileName: "/audio/bonfire.mp3",
  },
  {
    name: "大雨",
    fileName: "/audio/rain.mp3",
  },
  {
    name: "雨打树叶",
    fileName: "/audio/rain-on-leaves.mp3",
  },
  {
    name: "水下",
    fileName: "/audio/underwater.mp3",
  },
  {
    name: "细雨",
    fileName: "/audio/drizzle.mp3",
  }

]
</script>

<template>
  <div class="noise-player-container-wrapper">
    <div v-for="noise in noises" :key="noise.name" class="noise-player-container">
      <noise-player :noise="noise"></noise-player>
    </div>
  </div>

</template>

<style scoped>
.noise-player-container{
  width: calc(33% - 10px);
  margin-left: 10px;
}
.noise-player-container-wrapper{
  display: flex;
  flex-wrap: wrap;
}
</style>
