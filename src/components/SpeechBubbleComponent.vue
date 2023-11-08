<template>
<div class="speech-bubble-component">
    {{text}}
</div>
</template>
<script>
export default {
    name: 'SpeechBuuble',
    props: ["text"],
    data: function() {
        return {}
    },
    methods: {}
}
</script>
<style scoped>
.speech-bubble-component {
    position: relative;
    background: #00a9bb;
    border-radius: .4em;
}
.speech-bubble-component:after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    width: 0;
    height: 0;
    border: 51px solid transparent;
    border-top-color: #00a9bb;
    border-bottom: 0;
    border-left: 0;
    margin-left: -25.5px;
    margin-bottom: -51px;
}
</style>
