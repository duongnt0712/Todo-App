<template>
  <div class="container">
    <HeaderItem @toggle-add-task="toggleAddTask" title="Task Tracker" :showAddTask="showAddTask" />
    <router-view :showAddTask="showAddTask"></router-view>
    <FooterItem />   
  </div>
</template>

<script>
import HeaderItem from './components/Header'
import FooterItem from './components/Footer'

export default {
  name: 'App',
  components: {
    HeaderItem,
    FooterItem,
  },
  data() {
    return {
      showAddTask: false,
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100&display=swap');

#app {
  font-family: 'Poppins', sans-serif;
  font-weight: bold;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  border: 1px solid #333;
  padding: 20px;
}

.btn-style {
  display: inline-block;
  color: #fff;
  background: #333;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
