<template>
  <div class="project {{project.class}} project-{{index}}" v-on:click="clicked">
    <a href="{{project.url}}" target="_blank">
      <h2>{{project.name}}</h2>
      <p class="desc">{{project.desc}}</p>
      <div class="overlay">
        <h2>{{project.role}}</h2>
        <p>{{project.technologies}}</p>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  props: ['project', 'index', 'show'],
  methods: {
    clicked () {
      this.show = !this.show
      this.$dispatch('toggle-overlay', this.show)
    }
  }
}
</script>

<style scoped>
  .project {
    width: 100%;
    height: 100%;
    display: inline-block;
    position: relative;
    cursor: pointer;
    text-align: center;
  }

  .project a {
    text-decoration: none;
  }

  .project h2 {
    padding: 25px;
    padding-bottom: 0;
  }

  .project .overlay {
    text-align: center;
    color: #fff;
    position: absolute;
    background-color: rgba(0,0,0,.8);
    top: 0;left: 0;right: 0;bottom: 0;
    opacity: 0;
    transition: opacity .5s ease;
  }

  .desc {
    height: 100px;
  }

  h2 {
    height: 100px;
  }

  .project:hover .overlay {
    opacity: 1;
    transition: opacity .5s ease;
  }

  .project p {
    padding: 25px;
    text-align: center;
  }

  .conquest {
    background-color: #212D3B;
  }

  .conquest a {
    color: #fff;
  }

  .moodlr {
    background-color: #4A90E2;
  }

  .moodlr a {
    color: #fff;
  }

  .striply {
    background-color: #f5e774;
  }

  .striply a {
    color: #333;
  }

  .infinity {
    background-color: #0B131C;
  }

  .infinity a {
    color: #fff;
  }

  .worldia {
    background-color: #63C6AE;
  }

  .worldia a {
    color: #fff;
  }

  .lpf {
    background-color: #0099CC;
  }

  .lpf a {
    color: #fff;
  }

  .vsl {
    background-color: #3D454B;
  }

  .vsl a {
    color: #fff;
  }

  .perso {
    background-color: #e74c3c;
  }

  .perso a {
    color: #fff;
  }

  .appear-transition {
    transition: all 1s ease;
    opacity: 1;
  }

  /* .appear-enter defines the starting state for entering */
  /* .appear-leave defines the ending state for leaving */
  .appear-enter, .appear-leave {
    opacity: 0;
  }
</style>
