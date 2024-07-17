<template>
  <div id="app">
    <!-- <FireworksToText></FireworksToText> -->
    <!-- <img src="@/assets/logo.png" alt="Person" class="background-person"> -->
     <BirthdayMessage/>
     <FireworksDisplay/>
    <img src="@/assets/lan.png" alt="Person" class="background-person">
    <img src="@/assets/cake.png" alt="Person" class="background-cake">
  
  </div>
</template>

<script>
import BirthdayMessage from './components/BirthdayMessage.vue';
import FireworksDisplay from './components/FireworksDisplay.vue';
// import FireworksToText from './components/FireworksToText.vue';


export default {
  name: 'App',
  components: {
    BirthdayMessage,
    FireworksDisplay,
    // FireworksToText
  }
}
</script>

<style>
#app {
  position: absolute;
  width: 99%;
  height: 99%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.background-person {
  position: absolute;
  top: 20%;
  left: 50%;
  transform: translate(-50%, -50%);
  opacity: 0.09;
  width: 300px;
  height: auto;
  z-index: 1;
}
.background-cake {
  position: absolute;
  top: 87%;
  left: 50%;
  transform: translate(-50%, -50%);
  opacity: 0.3;
  width: 200px;
  height: auto;
  z-index: 1;
}
</style>
