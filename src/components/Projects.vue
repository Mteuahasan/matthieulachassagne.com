<template>
  <div id="showcase">
    <div v-for="(index, project) in projects">
      <project :project="project" :index="index" :show="show" transition="appear" transition-mode="out-in" v-if="visible"></project><!--
      -->
    </div>
  </div>
</template>

<script>
import Project from './Project'

export default {
  props: ['show'],
  components: {
    Project
  },
  data () {
    return {
      visible: false,
      projects: [{
        name: 'Conquest',
        desc: 'Multiplayer Online RTS game in browser',
        role: 'Front-end developer',
        technologies: 'HTML / CSS / JavaScript / Gulp',
        class: 'conquest',
        url: 'http://conquest.io'
      }, {
        name: 'Worldia',
        desc: 'SaaS for customizing trips. Worked on v2 not yet released',
        role: 'Front-end developer',
        technologies: 'HTML / CSS / AngularJS / Symfony2 / CircleCi',
        class: 'worldia',
        url: 'http://worldia.com'
      }, {
        name: 'Moodlr',
        desc: 'Tweeter like for moods',
        role: 'Back-end developer',
        technologies: 'Ruby on Rails / Rspec / Heroku / CircleCi / Travis',
        class: 'moodlr',
        url: 'http://moodlr.herokuapp.com'
      }, {
        name: 'Les petits frenchies',
        desc: 'French fashion blog and e-shop',
        role: 'Wordpress developer',
        technologies: 'WordPress / HTML / CSS / JavaScript',
        class: 'lpf',
        url: 'http://lespetitsfrenchies.fr'

      }, {
        name: 'Striply',
        desc: 'Online portfolio for comic strip artists',
        role: 'Lead developer',
        technologies: 'FatFreeFramework / HTML / Sass / JavaScript / Gulp',
        class: 'striply',
        url: 'https://github.com/Mteuahasan/backend-project-hetic'
      }, {
        name: 'Versailles Sciences Lab',
        desc: 'Insitutional website for the Versaille University',
        role: 'Wordpress developer',
        technologies: 'WordPress / HTML / CSS / JavaScript',
        class: 'vsl',
        url: 'http://vsl.prism.uvsq.fr/'
      }, {
        name: 'Infinity',
        desc: 'Galactic physics simulation',
        role: 'Physics & WebGL hacker',
        technologies: 'WebGL',
        class: 'infinity',
        url: 'http://matthieulachassagne.com/infinity'
      }, {
        name: 'This website',
        desc: 'is a portfolio.',
        role: 'Web development',
        technologies: 'Vue.js / Webpack / Babel',
        class: 'perso',
        url: 'http://github.com/mteuahasan'
      }, {
        name: 'Coming soon',
        desc: 'other stuffs...',
        role: 'including...',
        technologies: 'React.js / Electron...',
        class: ''
      }]
    }
  },
  ready () {
    this.visible = true
  }
}
</script>

<style>
  #showcase {
    width: 100%;
    height: 50%;
    position: absolute;
    bottom: 0;
    top: 50%;
  }

  #showcase > div {
    float: left;
    width: 33.3333%;
    height: auto;
    display: inline-block;
  }
</style>
