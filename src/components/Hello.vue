<template>
<div>
<transition name="fade">
	<home v-on:go="gettext" v-if="shift"></home>
  <addoil :propdata="content" v-if="!shift"></addoil>
</transition>
</div>
</template>

<script>
import request from 'superagent';
import Home from './home';
import Addoil from './addoil';

export default {
  name: 'hello',
  data() {
    return {
      content: '',
      shift: true,
    };
  },
  components: {
    Home, Addoil,
  },
  methods: {
    gettext() {
      request
        .get('/result')
        .end((err, res) => {
          if (err) throw err;
          this.content = res.body;
          setTimeout(() => {
            this.shift = false;
          }, 3000);
        });
    },
    slide() {
      this.$parent.ccnubox();
    },
  },
};
</script>
<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter, .fade-leave-active {
  opacity: 0
} 
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
