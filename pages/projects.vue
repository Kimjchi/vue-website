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
        description: '"Artificial intelligence by ideMobi for relationships" is a project I am currently working on.\n' +
        'The goal is to create a tool for video games editors to use on Unity.\n' +
        'This tool will allow you to manage social relationships between characters ! ',
        link: ''
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
