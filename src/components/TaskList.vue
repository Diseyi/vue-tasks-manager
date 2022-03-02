<template>
  <div class="">
    <h3 class=" ">{{ task.text }}</h3>
    <span class="font-semibold text-sm"> {{ task.day }} </span>
  </div>
</template>

<script>
export default {
  name: "TaskList",
  props: {
    task: Object,
  },
};
</script>

<style>
</style>