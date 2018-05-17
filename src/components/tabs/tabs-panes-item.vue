<template>
  <div class="tabs-panes-item" :class={active}  v-show="active">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    props: ['name'],
    data () {
      return {
        selectedTab: ''
      }
    },
    computed: {
      active () {
        return this.selectedTab === this.name
      }
    },
    methods: {
      selectTab (selectedTab) {
        this.selectedTab = selectedTab
      }
    }
  }
</script>

<style>

</style>