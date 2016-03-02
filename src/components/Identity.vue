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
    let self = this
    self.interval = setInterval(() => {
      let j = 0
      self.skill = ''
      self.secondInterval = setInterval(() => {
        self.skill += self.skills[i][j]
        j++
        if (j === self.skills[i].length) {
          j = 0
          clearInterval(self.secondInterval)
        }
      }, base)
      i++
      if (i === self.skills.length) i = 0
    }, time)
    window.addEventListener('blur', function () {
      console.log('nope')
      clearInterval(self.interval)
    }, false)
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

  @media screen and (max-width: 620px) {
    .identity p {
      font-size: 1.5em;
      padding-top: 0px;
    }
  }

  .identity p span {
    color: #e74c3c;
  }
</style>
