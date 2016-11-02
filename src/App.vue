<template>
  <div id="app">
  <transition name="fade">
    <hello v-if="!tobox"></hello>
    <box v-if="tobox"></box>
  </transition>
  </div>
</template>

<script>
import Hello from './components/Hello';
import Box from './components/ccnubox';

export default {
  name: 'app',
  data() {
    return {
      tobox: false,
    };
  },
  components: {
    Hello, Box,
  },
  methods: {
    ccnubox() {
      if (this.tobox === true) {
        return;
      }
      this.tobox = true;
    },
  },
};
</script>

<style lang='scss' scoped>
@import '../static/common.scss';
@font-face {
  font-family: 'zcool';
  src: url('../static/jianti.ttf') format('truetype');
}
.hidden{
  display: none;
}
#app {
/*  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;*/
  width: 100%;
  height: 100%;
  background: url('./sprite/sprite.png') no-repeat;
  background-size:100%;
  @include sprite__position($bgimg,2208px);
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter, .fade-leave-active {
  opacity: 0
} 
</style>
