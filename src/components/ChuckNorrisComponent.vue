<template>
  <div id="chuck-norris">
    <p>I am Chuck Norris</p>
    <speech-bubble v-if="currentJoke" :text="currentJoke"></speech-bubble>
    <img src="../assets/chuck.jpg" id="chuck-norris__image" >
    <button @click="fetchRandomJoke">
      Tell me a joke
    </button>
  </div>
</template>

<script>
import SpeechBubble from './SpeechBubbleComponent.vue';

const API_RANDOM_JOKE_ENDPOINT = 'https://api.chucknorris.io/jokes/random';

export default {
  name: 'ChuckNorris',
  components: {
    'speech-bubble': SpeechBubble
  },
  data() {
    return {
      currentJoke: null
    };
  },
  methods: {
    fetchRandomJoke() {
      fetch(API_RANDOM_JOKE_ENDPOINT)
        .then(response => {
          if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
          }
          return response.json();
        })
        .then(data => {
          console.log(data);
          this.currentJoke = data.value;
        })
        .catch(error => {
          console.error('There was an error fetching the joke:', error);
          this.currentJoke = 'Failed to fetch joke.';
        });
    }
  }
};
</script>

<style scoped>
#chuck-norris {
    position: relative;
}
#chuck-norris__joke__container {
    position: absolute;
    top: 0;
    right: 0;
}
#chuck-norris__image {
    height: 200px;
    transition: all 0.2s ease-in;
}
</style>
