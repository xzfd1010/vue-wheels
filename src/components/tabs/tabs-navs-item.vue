<template>
  <!--这里是对象语法-->
  <div class="tabs-navs-item" :class={active} @click="changeTab">
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
      },
      changeTab () {
        console.log("儿子发射了")
        this.$emit('update:selectedTab', this.name)
      }
    }
  }
</script>

<style>

</style>