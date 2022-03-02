<template>
  <header class="flex flex-row justify-between p-6  ">

    <h2 class="font-semibold text-2xl ">{{ title }}</h2>
    <Button
    text='Add task'
    color='green'
     />

  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "AppHeader",
  components: {
    Button,
  },
  //props as array
  // props: ['title'],
  // props as object
  props: {
    title: {
      type: String,
      default: "Hello World",
    },
  },
};
</script>

<style>
</style>