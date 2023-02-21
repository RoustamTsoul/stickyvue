<template>
  <div class="container">
    <CreateSticky/>
  </div>
  
</template>

<script>
import CreateSticky from './components/CreateSticky.vue'

export default {
  name: 'App',
  components: {
    CreateSticky
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lacquer&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Big+Shoulders+Inline+Text&display=swap');
*{
/* padding: 0;
margin: 0; */
}

body{
background:radial-gradient(ellipse at 50% 30%,rgba(167, 56, 80, 1), rgba(45, 37, 38, 1), rgba(196, 102, 77, 1));
height: 100vh;
}

.container{
width: 100%;
margin: auto;
}
</style>
