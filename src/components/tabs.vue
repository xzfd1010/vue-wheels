<template>
  <div class="tabs">
    <ol class="tabs-bar">
      <li v-for="(item,index) in tabsBarName" @click="selectTab(index)" :class="{active: activeIndex === index}">
        {{item}}
      </li>
    </ol>
    <ol class="tabs-content">
      <slot name="tab-content" v-for="(item,index) in tabsContent" :item="item" :index="index" :activeIndex="activeIndex"></slot>
    </ol>
  </div>
</template>
<script>
  export default {
    name: '',
    props: {
      tabsBarName: {
        type: Array,
        default: () => {
          return [1, 2, 3]
        }
      },
      tabsContent: {
        type: Array,
        default: () => {
          return [1, 2, 3]
        }
      }
    },
    data() {
      return {
        activeIndex: 0
      }
    },
    methods: {
      selectTab(index) {
        this.activeIndex = index
      }
    }
  }
</script>

<style>
  .tabs {
  }

  .tabs > ol {
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .tabs > ol.tabs-bar {
    display: flex;
    border-bottom: 1px solid red;
  }

  .tabs > ol.tabs-bar > li {
    padding: 4px 8px;
    border: 1px solid transparent;
    border-bottom: 0;
  }

  .tabs > ol.tabs-bar > li:hover {
    border-color: red;
  }

  .tabs > ol.tabs-bar > li.active {
    border-color: blue;
  }

  .tabs > ol.tabs-content > li {
    display: none;
  }

  .tabs > ol.tabs-content > li.active {
    display: block;
  }
</style>
