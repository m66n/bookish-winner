<template>
  <div id="app">
    <div class="columns is-mobile is-centered">
      <div class="column is-narrow">
        <Card :show="show"/>
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

export default {
  name: 'App',
  components: {
    Card
  },
  data () {
    return {
      show: false
    }
  },
  methods: {
    next () {
      this.show = false
    },
    reset () {
      this.show = false
    }
  }
}
</script>

<style lang="scss">
#app {
  padding-top: 2em;
}
</style>
