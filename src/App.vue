<template>
  <div id="app">
    <tabs :selectedTab.sync="selectedTab">
      <tabs-navs>
        <tabs-navs-item name="ChoiceQuestion">选择题</tabs-navs-item>
        <tabs-navs-item name="ClozeQuestion">填空题</tabs-navs-item>
      </tabs-navs>
      <tabs-panes>
        <tabs-panes-item name="ChoiceQuestion">1</tabs-panes-item>
        <tabs-panes-item name="ClozeQuestion">2</tabs-panes-item>
      </tabs-panes>
    </tabs>
  </div>
</template>

<script>
  import Tabs from './components/tabs/tabs'
  import TabsNavs from './components/tabs/tabs-navs'
  import TabsNavsItem from './components/tabs/tabs-navs-item'
  import TabsPanes from './components/tabs/tabs-panes'
  import TabsPanesItem from './components/tabs/tabs-panes-item'

  export default {
    name: 'App',
    data () {
      return {
        selectedTab: 'ChoiceQuestion'
      }
    },
    components: {
      Tabs,
      TabsNavs,
      TabsNavsItem,
      TabsPanes,
      TabsPanesItem
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
  .tabs-navs{
    display: flex;
  }
  .tabs-navs-item{
    margin-right:10px;
  }
  .active {
    background: deepskyblue;
  }
</style>
