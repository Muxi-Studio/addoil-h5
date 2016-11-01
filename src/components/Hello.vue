<template>
<div class="background">
	<home></home>
	<addoil></addoil>
</div>
</template>

<script>
import Home from './home';
import Intro from './intro';
import Addoil from './addoil';

export default {
  name: 'hello',
  components: {
    Home, Intro, Addoil,
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
@import '../../static/mixins/_sprite.scss';
.background{
	position: relative;
	width: 100%;
	height: 100%;
  @include sprite($bgimg);
  background-size: 100%;
  text-align: center;
}
</style>
