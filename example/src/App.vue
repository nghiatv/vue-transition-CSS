<template>
  <div id="app">
    <button v-on:click="show = !show">
      Toggle
    </button>
    <h2>Look at the picture</h2>
    
    <div class="left">
      <transition name="slide-fade">
      <div class="vuong1 blue" v-if="show" ></div>
    </transition>
    <transition name="fade">
      <div v-on:click="show = !show" class="vuong1" v-if="show"></div>
    </transition>
    
    </div>
    <div class="right">
      <transition name="bounce">
      <div class="vuong1 red" v-if="show" ></div>
    </transition>
     <transition name="" 
     enter-active-class="animated tada"
      leave-active-class="animated bounceOutRight"
      >
      <div class="vuong1" v-if="show"
        ></div>
    </transition>

    <transition name="dunno">
      <div class="vuong1 blue" v-if="show" ></div>
    </transition>
    
    </div>
    </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      show: true,
      red:true
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.left,.right {
  float: left;
  width: 50%;
  height: 75vh;
}
.vuong1{
  width: 150px;
  height: 150px;
  background-color: #42b983;
  margin: 10px;
  flex:1;
  flex-direction: center center;

}
.red{
  background: red;
}
.blue{
  background: blue;
}
h1, h2 {
  font-weight: normal;
}


/*test transition*/
.fade-enter-active, .fade-leave-active {
  transition: opacity 1s
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0
}

/* durations and timing functions.              */
.slide-fade-enter-active {
  transition: all .5s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to{
  transform: translateX(10px);
  opacity: 0;
}
.dunno-enter-active {
  transition: all 2s ease
}
.dunno-leave-active {
  transition: all 3s cubic-bezier(2.0, 1.5, 0.3, 1.6);
}
.dunno-enter, .dunno-leave-active{
  transform: translateY(20px);
}
/*animation*/

.bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-out .5s;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
@keyframes bounce-out {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(0);
  }
}
</style>
