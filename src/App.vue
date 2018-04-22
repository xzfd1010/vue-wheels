<template>
  <div id="app">
    <tabs>
      <li slot="tab-content" slot-scope="props" :class="{active: props.activeIndex === props.index}">{{props.item}}</li>
    </tabs>
  </div>
</template>

<script>
  import Tabs from './components/tabs'

  export default {
    name: 'App',
    components: {
      Tabs
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
</style>
