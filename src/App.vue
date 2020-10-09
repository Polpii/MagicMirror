<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Pose/>
    <WeatherApp id = "weatherblock" :class="period"></WeatherApp>

  </div>
</template>
<script src = "./socket.js"> </script>
<script>
//import HelloWorld from './components/HelloWorld.vue'
import Pose from './components/Pose.vue'
import WeatherApp from './components/WeatherApp'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    Pose,
    WeatherApp
  },
  data() {
    return {
      date: new Date
    }
  },

  computed: {
    year() {
      return this.date.getFullYear();
    },

    period() {
      let hour = this.date.getHours();

      return (hour > 5 && hour < 18)? 'app--day': 'app--night';
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#weatherblock{
  position: fixed;
  right :0;
  top :0;
}
body{
	background: black;
}

</style>
