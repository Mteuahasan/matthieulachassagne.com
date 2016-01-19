<template>
  <div class="identity">
    <h1>Matthieu Lachassagne</h1>
    <h2>full-stack padawan</h2>
    <p>I <span>❤</span> {{ skill }}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      skills: ['JavaScript', 'Rails', 'React.js', 'Vue.js', 'and more'],
      skill: 'Javascript'
    }
  },
  ready () {
    let i = 0
    let skills = this.skills.slice(0)
    let longest = skills.sort(function (a, b) { return b.length - a.length })[0]
    let length = longest.length
    let base = 200
    let time = 200 * length + 1000
    this.interval = setInterval(() => {
      let j = 0
      this.skill = ''
      this.secondInterval = setInterval(() => {
        this.skill += this.skills[i][j]
        j++
        if (j === this.skills[i].length) {
          j = 0
          clearInterval(this.secondInterval)
        }
      }, base)
      i++
      if (i === this.skills.length) i = 0
    }, time)
  },
  beforeDestroy () {
    clearInterval(this.interval)
    clearInterval(this.secondInterval)
  }
}
</script>

<style>
  h1 {
    font-family: "Raleway", sans-serif;
    font-weight: 100;
    font-size: 4em;
    text-align: center;
    margin: 0;
  }
  h2 {
    text-align: center;
    font-weight: lighter;
    font-size: 1.5em;
  }
  .identity {
    height: 50%;
    position: fixed;
    left: 0;right: 0;
    padding-top: 50px;
  }

  .identity p {
    font-size: 2em;
    text-align: center;
    padding-top: 90px;
  }

  .identity p span {
    color: #e74c3c;
  }
</style>
