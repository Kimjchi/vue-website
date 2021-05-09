<template>
  <v-container fluid>
    <v-container style="padding: 5% 0">
      <h1 style="font-size: 3em;" class="text-center">I like trains and smile a lot.</h1>
    </v-container>
    <v-container>
      <img :src="illustration" style="max-height: 100%; max-width: 100%"/>
      <div class="text-caption" style="font-size: 1rem; opacity: 0.5;">How I think I look.</div>
    </v-container>
    <v-container class="text-center">
      <h2 style="margin-bottom: 3%">Jérémy Kim</h2>
      <p class="text-justify">
        I'm a French Data Scientist graduated recently from an engineering school and back in Paris.
        After interning 6 months at Smartly.io, I decided to continue my job there as this place is full of extraordinary people.
        I don't know if this is the right way for me but I want to keep going and give it a shot.<br>
        <br>
        In between work, I like to balance between watching movies, reading books and trying creative projects. I also try to add some sport here and there.
        I would like to be a more creative person but I'm lazy as hell (which makes me a good programmer). <br>
        <br>
        I coded this website in one day to motivate me and (kinda) learn vue js.
        Now, there is a place where I can dump my drawings, writings and future comics. Knowing that people can see this stuff is a good motivation to move my lazy bum.
        Be it bad or very bad, I will put (most of) all my work here.<br>
        <br>
        Thanks for reading this. Please reach out if you wanna talk.
      </p>
      <v-btn
        outlined
        style="margin: 6%"
        to="/contact"
      >
        Let's talk
      </v-btn>
    </v-container>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        illustration: require('~/assets/queen.jpeg')
      }
    }
  }
</script>

<style scoped>
  div { font-family: Europa, sans-serif }
  h1 {
    font-size: 20px;
  }
  p {
    margin: 0 10%;
  }
</style>
