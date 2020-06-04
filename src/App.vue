<template>
  <div id="app">
    <div class="columns is-mobile is-centered">
      <div class="column is-narrow">
        <Card :show="show" :current="nato[current]"/>
      </div>
    </div>
    <div class="columns is-mobile is-centered">
      <div class="column is-narrow">
        <div class="field is-grouped">
          <p class="control">
            <button class="button" @click="show = true" :disabled="show">Show</button>
          </p>
          <p class="control">
            <button class="button" @click="next()">Next</button>
          </p>
          <p class="control">
            <button class="button" @click="reset()">Reset</button>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'
import nato from './data/nato'

export default {
  name: 'App',
  components: {
    Card
  },
  data () {
    return {
      show: false,
      nato: nato,
      current: 0
    }
  },
  methods: {
    next () {
      this.show = false
      if (this.current < this.nato.length - 1) {
        this.current += 1
      }
    },
    reset () {
      this.show = false
      this.current = 0
    }
  }
}
</script>

<style lang="scss">
#app {
  padding-top: 2em;
}
</style>
