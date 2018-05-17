<template>
  <div class="tabs-panes">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        selectedTab: ''
      }
    },
    mounted () {
      this.$children.forEach(vm => {
        vm.selectTab(this.selectedTab)
      })
      this.$on('update:selectedTab', (selectedTab) => {
        this.$emit('update:selectedTab', selectedTab)
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