<template>
  <button @click='onClick() ' class=" px-4 py-1 text-white font-semibold rounder " :style="{background: color}" >{{text}} </button>
</template>

<script>
export default {
name: 'Button',
  props: {
    text: String,
    color: String,
  },

  methods: {
      onClick() {
          console.log('click')
      }
  }
}
</script>

<style>

</style>