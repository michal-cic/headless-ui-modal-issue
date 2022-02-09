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
        <!--
          Pass the `isOpen` ref to the `open` prop, and use the `close` event
          to set the ref back to `false` when the user clicks outside of
          the dialog or presses the escape key.
        -->
        <Dialog :open="isOpen" @close="setIsOpen">
          <DialogOverlay />

          <DialogTitle>Deactivate account</DialogTitle>
          <DialogDescription>
            This will permanently deactivate your account
          </DialogDescription>

          <p>
            Are you sure you want to deactivate your account? All of your data will be
            permanently removed. This action cannot be undone.
          </p>

          <!--
            You can render additional buttons to dismiss your dialog by setting your
            `isOpen` state to `false`.
          -->
          <button @click="setIsOpen(false)">Cancel</button>
          <button @click="handleDeactivate">Deactivate</button>
        </Dialog>
      </TabPanel>
      <TabPanel>Content 3</TabPanel>
    </TabPanels>
  </TabGroup>
</template>

<script>
  import {
    TabGroup,
    TabList,
    Tab,
    TabPanels,
    TabPanel,
    Dialog,
    DialogOverlay,
    DialogTitle,
    DialogDescription
  } from '@headlessui/vue'
  import { ref } from "vue";

  export default {
    components: {
      TabGroup,
      TabList,
      Tab,
      TabPanels,
      TabPanel,
      Dialog,
      DialogOverlay,
      DialogTitle,
      DialogDescription,
    },
    methods: {
      tabChange(index) {
        console.log('tabChange()', index);
      }
    },
    setup() {
      // The open/closed state lives outside of the Dialog and
      // is managed by you.
      let isOpen = ref(false);

      return {
        isOpen,
        setIsOpen(value) {
          isOpen.value = value;
        },
        handleDeactivate() {
          // ...
        }
      };
    },
  }
</script>
