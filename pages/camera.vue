<script setup lang="ts">
const camera = useAsyncData(
  "camera",
  () =>
    navigator.mediaDevices.getUserMedia({
      video: {
        facingMode: {
          exact: "environment",
        },
      },
    }),
  {
    server: false,
    immediate: false,
  }
);

const source = ref<HTMLVideoElement>();

watch(camera.data, () => {
  if (source.value) {
    source.value.srcObject = camera.data.value;
  }
});
</script>

<template>
  <h1 class="langdex-heading-xl">Good morning user</h1>
  <button v-on:click="camera.execute()">Take photo</button>
  <video ref="source" autoplay></video>
</template>

<style scoped>
video {
  width: 250px;
  height: 400px;
}
</style>
