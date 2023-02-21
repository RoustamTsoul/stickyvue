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
background-image: linear-gradient(to bottom, #121025, #12263e, #073d56, #005569, #006e76, #007b73, #218769, #48925a, #6a9242, #8d8f2f, #af8927, #d17e32);
height: 100vh;
}

.container{
width: 100%;
margin: auto;
}
</style>
