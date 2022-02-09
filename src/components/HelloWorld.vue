<template>
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
</template>

<script>
  import { ref } from "vue";
  import {
    Dialog,
    DialogOverlay,
    DialogTitle,
    DialogDescription,
  } from "@headlessui/vue";

  export default {
    components: { Dialog, DialogOverlay, DialogTitle, DialogDescription },
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
  };
</script>
