<template>
  <header>
    <h1>{{ title }}</h1>
    <ButtonItem v-show="homePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask?'Close':'Add Task'" />
  </header>
</template>

<script>
import ButtonItem from './Button';

export default {
  name: 'HeaderItem',
  props: {
    title: String,
    showAddTask: Boolean
  },
  components: {
    ButtonItem
  },
  computed: {
    homePage() {
      if(this.$route.path === '/') {
        return true
      } else {
        return false
      }
    }
  }
}
</script>

<style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
</style>