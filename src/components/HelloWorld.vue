<template>
  <div>
    <h1>Список треков</h1>
    <audio controls ref="audioElement">
      <source class="audio-style" :src="trackUrl" type="audio/mp3">
    </audio>
    <button @click="speedUp">Ускорить</button>
    <button @click="slowDown">Замедлить</button>
    <button @click="init">Вернуть назад</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      tracks: [
        {name: "Трек 1", speed: 1.0},
        {name: "Трек 2", speed: 1.0},
        {name: "Трек 3", speed: 1.0}
      ],
      trackUrl: "src/audio/track.mp3"
    };
  },
  methods: {
    speedUp() {
      const audioElement = this.$refs.audioElement;
      audioElement.playbackRate += 0.5; // Увеличить скорость на 0.1
    },
    slowDown() {
      const audioElement = this.$refs.audioElement;
      audioElement.playbackRate -= 0.2; // Уменьшить скорость на 0.1
    },
    init() {
      const audioElement = this.$refs.audioElement;
      audioElement.playbackRate = 1;
    },
  },
};
</script>

<style>

</style>