<script setup lang="ts">
const camera = useAsyncData("camera", () => window.navigator.mediaDevices.getUserMedia({
  video: {
    facingMode: {
      exact: "environment"
    }
  }
}), {
  server: false, 
  immediate: false
});

const source = ref<HTMLVideoElement>();
</script>

<template>
 <h1 class="langdex-heading-xl">Good morning user</h1>
 <button @click="() => {
  camera.execute();
  // fix on first click only works on second
  if (camera.data && source) {
    source.srcObject = camera.data.value;
  }
 }">Take photo</button>
 <video ref="source" autoplay></video>
</template>

<style scoped>
video {
  width: 250px;
  height: 400px;
}
</style>