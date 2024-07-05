<script setup>
import {defineProps, onMounted, ref, watch} from 'vue'
const volume = ref(100);
const isPlaying = ref(false);
let audio =null;
const props=defineProps({
  noise:{
    type:Object,
    required:true
  }
})
onMounted(()=>{
  audio = document.getElementById(props.noise.name);
  audio.src = props.noise.fileName;
})
watch(volume, (newVal, oldVal) => {
  audio.volume = newVal / 100;
})
watch(isPlaying, (newVal, oldVal) => {
  if (newVal) {
    audio.play();
  } else {
    audio.pause();
  }
})
</script>

<template>
  <div class="noise-player">
    <h1>{{props.noise.name}}</h1>
    <audio :id="props.noise.name"  controls loop style="display:none"></audio>
    <a-switch v-model:checked="isPlaying" />
    <a-slider id="test" v-model:value="volume"  />
  </div>

</template>

<style scoped>
.noise-player {
  width: 70%;
  margin: 0 auto;
}
</style>