<template>
  <div class="speech-bubble">
    {{text}}
  </div>
</template>
<script>
export default {
    name: 'SpeechBubbleComponent',
    props: ["text"],
    data: function() {
        return {}
    },
    methods: {}
}
</script>
<style scoped>
.speech-bubble {
  position: relative;
  background: #f4f4f4;
  border-radius: 10px;
  padding: 10px 20px;
  margin: 10px;
  color: #333;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  max-width: 300px;
  left: 50%;
}

.speech-bubble:after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 0;
  border: 10px solid transparent;
  border-top-color: #f4f4f4;
  border-bottom: 0;
  margin-left: -10px;
  margin-bottom: -10px;
}
</style>
