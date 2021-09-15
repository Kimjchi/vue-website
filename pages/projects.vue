<style scoped>
  div { font-family: Europa, sans-serif }
  h1 {
    font-size: 20px;
    text-align: center;
  }
  p {
    margin: 0 10%;
  }
  img {
    cursor: pointer;
  }
</style>

<template>
  <v-container fluid>
    <modal-component v-if="showModal" @close="showModal = false" v-bind:link=modalLink>
      <template slot="modal-header"> {{ modalTitle }} </template>
      <template slot="modal-text"> {{ modalDescription }} </template>
    </modal-component>
    <v-container>
      <v-row>
        <v-col
          v-for="item in items"
          :key="item.path"
          cols="12" lg="6"
        >
          <img :src="item.path" style="max-height: 100%; max-width: 100%" @click="showModalFn(item)"/>
          <h1>{{ item.name }}</h1>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
import ModalComponent from '../components/Modal.Vue';

export default {
  components: {
    ModalComponent
  },
  data () {
    return {
      showModal: false,
      modalTitle: '',
      modalDescription: '',
      modalLink: '',
      items: [{
        name: 'Pandocreon divinae',
        path: require('@/assets/project_images/pandocreon.png'),
        description: 'Pandocreon divinae is a card game that we had to implement in Java for a school project.\n' +
          'This game is my first real programming experience.\n' +
          'It taught me the basics of sofware engineering: from UML analysis to management and control process.',
        link: 'https://github.com/Kimjchi/Pandocreon'
      }, {
        name: 'Credit Calculator',
        path: require('@/assets/project_images/projetLO07.png'),
        description: 'This website is a redesign of our school\'s website to display the students\' grades.\n' +
          'For this project, we used PHP as a programming language and used mySQL for the database.',
        link: 'http://jeremykim.fr/projet-lo07/'
      }, {
        name: 'CRM',
        path: require('@/assets/project_images/CRM.png'),
        description: 'During my semester at the University of Sherbrooke, I worked on a CRM (Client Relationship Manager) with a group of six people.\n' +
          'We worked with a real company and created the CRM from scratch using react for the front-end, NodeJs for the back-end and PostgresSQL for our database.\n' +
          'This project was quite meaningful for me because I was able to learn a lot in project management and programming skills.',
        link: ''
      }, {
        name: 'One Point Man',
        path: require('@/assets/project_images/onepointman.png'),
        description: 'Another project I worked on at the University of Sherbrooke is "Onepointman".\n' +
          'It\'s a web application as well as an Android application. The goal of this project was to work with the geolocalisation of a smartphone with Android.\n' +
          'You can pinpoint your friends on a map if they enable their location and you can even draw on this map !\n' +
          'We used react, Java and the facebook API to program this application.',
        link: 'https://github.com/Kimjchi/onepointman'
      }, {
        name: 'Junior conseil UTT',
        path: require('@/assets/project_images/projetJunior.png'),
        description: 'The purpose of a junior is to find companies with projects, find students\n' +
          'with the ability to complete those projects, and to manage the relationship\n' +
          'between the company and the student. As vice-treasurer and project manager,\n' +
          'I was able to learn accounting and project management from this experience.',
        link: 'https://jc-utt.fr/'
      }, {
        name: 'App Ravenous',
        path: require('@/assets/project_images/projetRavenous.png'),
        description: 'This is a yelp like web application\n' +
        'that search and list restaurants depending on the location of your choice.\n' +
        'This web app was made during a codecademy formation.\n' +
        'For this project, I used react and the yelp API.',
        link: 'http://ravenous.jeremykim.fr/'
      }, {
        name: 'App Jammming',
        path: require('@/assets/project_images/projetJamming.png'),
        description: 'This web application allow you to search for musics, add them to a playlist\n' +
        'and add this playlist to your spotify account. ' +
        'This web app was also made during a codecademy formation. ' +
        'For this project, I used react and the spotify API.',
        link: 'http://jamming.jeremykim.fr/'
      }, {
        name: 'AIIR',
        path: require('@/assets/project_images/AIIR.png'),
        description: '"Artificial intelligence by ideMobi for relationships" is a project I worked on during my last school year.\n' +
        'The goal is to create a tool for video games editors to use on Unity.\n' +
        'This tool will allow you to manage social relationships between characters ! ',
        link: ''
      }, {
        name: 'Block Breaker',
        path: require('@/assets/project_images/BlockBreaker.png'),
        description: '"Block Breaker" is a small game I worked on to practice the basic functionalities of Unity.',
        link: 'http://jeremykim.fr/block-breaker/'
      }, {
        name: 'Laser Defender',
        path: require('@/assets/project_images/LaserDefender.png'),
        description: 'Continuing on the Unity course, I worked on this classic scroller space game to\n' +
        'learn new Unity tools such as VFXs, particles, Scriptable Objects, etc..',
        link: 'http://jeremykim.fr/Laser-Defender/'
      }, {
        name: 'Glitch Garden',
        path: require('@/assets/project_images/GlitchGarden.png'),
        description: 'This Unity game took the longest to make. A lot of new concepts were introduced during this course.\n' +
        'But the focus was on the animation tools. This game is based on the famous Plants vs Zombies game with a tower defense system.\n' +
        'This was a great opportunity for me to understand the animations, sprites and their relationships with the other components.',
        link: 'http://jeremykim.fr/Glitch-Garden/'
      }, {
        name: 'Tilevania',
        path: require('@/assets/project_images/Tilevania.png'),
        description: 'The last Unity game of the Udemy course. I was able to learn tiles, tilemaps and how we can\n' +
        'easily build levels with them. Physics and collision also played a big part of this course.\n' +
        'This time, the game is a simple platformer where you need to reach the exit.',
        link: 'http://jeremykim.fr/Tilevania/'
      }, {
        name: 'Building Escape',
        path: require('@/assets/project_images/BuildingEscape.png'),
        description: 'The goal of this project was to play around with Unreal Engine and try its basic functionalities.',
        link: 'http://jeremykim.fr/block-breaker/'
      }, {
        name: 'Reddit Client',
        path: require('@/assets/project_images/RedditClient.png'),
        description: 'This project is part of a CodeCademy curriculum towards a Full-Stack Engineer certificate.\nThe reddit client is focused on the front-end ' +
        ' and allowed me to work on my React and Redux skills to manage the data flux. I was also able to work on a third party API to get Reddit\'s data.',
        link: 'https://kimjchi.github.io/reddit-client/'
      }]
    }
  },

  mounted() {
    //this.importAll(require.context('../assets/images/', false, /\.jpeg$/));
  },

  methods: {
    showModalFn: function (item) {
      this.showModal = true;
      this.modalTitle = item.name;
      this.modalDescription = item.description;
      this.modalLink = item.link;
    }
  },
}
</script>
