<template>
  <button @click="onClick()" class="btn-style">{{ text }}</button>
</template>

<script>
  export default {
    name: 'ButtonComp',
    props: {
      text: String,
    },
    methods: {
      onClick() {
        this.$emit('btn-click')
      }
    }
  }
</script>