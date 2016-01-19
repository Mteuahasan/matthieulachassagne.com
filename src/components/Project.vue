<template>
  <div class="project {{project.class}} project-{{index}}">
    <h2>{{project.name}}</h2>
    <p>{{project.desc}}</p>
    <div class="overlay">
      <h2>{{project.role}}</h2>
      <p>{{project.technologies}}</p>
    </div>
  </div>
</template>

<script>

export default {
  props: ['project', 'index'],
  data () {
    return {

    }
  },
  ready () {
    this.show = true
  }
}
</script>

<style>
  .project {
    width: 100%;
    height: 100%;
    display: inline-block;
    position: relative;
    cursor: pointer;
  }

  .project h2 {
    padding: 25px;
    padding-bottom: 0;
  }

  .project .overlay {
    color: #fff;
    position: absolute;
    background-color: rgba(0,0,0,.8);
    top: 0;left: 0;right: 0;bottom: 0;
    opacity: 0;
    transition: opacity .5s ease;
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
    color: #fff;
  }

  .moodlr {
    color: #fff;
    background-color: #4A90E2;
  }

  .striply {
    background-color: #f5e774;
    color: #333;
  }

  .infinity {
    background-color: #0B131C;
    color: #fff;
  }

  .worldia {
    background-color: #63C6AE;
    color: #fff;
  }

  .lpf {
    background-color: #0099CC;
    color: #fff;
  }

  .vsl {
    background-color: #3D454B;
    color: #fff;
  }

  .perso {
    background-color: #e74c3c;
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
