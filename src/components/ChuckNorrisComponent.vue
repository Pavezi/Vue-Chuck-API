<template>
  <div id="chuck">
    <p>I am Chuck! Chuck Norris</p>
    <speech-bubble-component v-if="currentJoke" :text="currentJoke"></speech-bubble-component>
    <img src="../assets/chuck.jpg" alt="Chuck Norris" id="chuck_img">
    <button @click="fetchRandomJoke">
      Chuck! Tell me a joke
    </button>
  </div>
</template>

<script>
import SpeechBubbleComponent from './SpeechBubbleComponent.vue';

export default {
  name: 'Chuck',
  components: {
    'speech-bubble-component': SpeechBubbleComponent
  },
  data() {
    return {
      currentJoke: '',
      error: null
    };
  },
  methods: {
    async fetchRandomJoke() {
      try {
        const response = await fetch('https://api.chucknorris.io/jokes/random');
        if (!response.ok) throw new Error(`HTTP error! status: ${response.status}`);
        const data = await response.json();
        this.currentJoke = data.value;
      } catch (error) {
        this.error = error.message;
      }
    }
  }
};
</script>

<style scoped>
#chuck {
    position: relative;
    text-align: center;
}

#chuck_img {
    height: 200px;
    margin-top: 10px;
    margin-bottom: 10px;
}
</style>
