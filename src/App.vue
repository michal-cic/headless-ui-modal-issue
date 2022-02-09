<template>
  <TabGroup @change="tabChange">
    <TabList>
      <Tab>Tab 1</Tab>
      <Tab>Tab 2</Tab>
      <Tab>Tab 3</Tab>
    </TabList>
    <TabPanels>
      <TabPanel>Content 1</TabPanel>
      <TabPanel>
        <HelloWorld />
      </TabPanel>
      <TabPanel>Content 3</TabPanel>
    </TabPanels>
  </TabGroup>
</template>

<script>
  import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue'
  import HelloWorld from './components/HelloWorld.vue'

  export default {
    components: {
      TabGroup,
      TabList,
      Tab,
      TabPanels,
      TabPanel,
      HelloWorld
    },
    methods: {
      tabChange(index) {
        console.log('tabChange()', index);
      }
    },
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
