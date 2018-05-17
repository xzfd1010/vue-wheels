<template>
  <div class="tabs-navs">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'tabs-navs',
    data () {
      return {
        selectedTab: ''
      }
    },
    mounted () {
      this.$children.forEach(vm => {
        vm.selectTab(this.selectedTab)
        vm.$on('update:selectedTab', (selectedTab) => {
          console.log('爸爸知道了')
          this.$emit('update:selectedTab', selectedTab)
        })
      })
    },
    methods: {
      selectTab (selectedTab) {
        this.selectedTab = selectedTab
        this.$children.forEach((vm)=>{
          vm.selectTab(selectedTab)
        })
      }
    }
  }
</script>

<style>

</style>