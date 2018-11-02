<template>
  <div id="app">
    <img src="./assets/logo.png">
    <child :selected="selected" name="main" @change="select"/>
    <child :selected="selected" name="second" @change="select"/>
    <child :selected="selected" name="other" @change="select"/>
    <child v-for="item in menus" :key="item" :selected="selected" :name="item" @change="select"/>
  </div>
</template>

<script>
import Child from './components/Child'

export default {
  name: 'App',
  data () {
    return {
      selected: 'main',
      menus: [
        'other1',
        'other2',
        'other3',
        'othern'
      ]
    }
  },
  methods: {
    select (newSelection) {
      this.selected = newSelection
    }
  },
  components: {
    Child
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
