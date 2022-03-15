<template>
  <footer>
    <p>Copyright &copy; 2022</p>
    <a href="/about">About</a>
  </footer>
</template>

<script>
export default {
  name: 'FooterItem',
}
</script>

<style scoped>
  footer {
    margin-top: 50px;
    text-align: center;
  }  
  p, a {
    margin: 0;
    padding: 0;
    color: #333;
  }
</style>