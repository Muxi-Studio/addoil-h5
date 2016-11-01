<template>
<div class="background">
	<home></home>
<!-- 	<addoil></addoil> -->
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
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
@import '../../static/common.scss';
.background{
	position: relative;
	width: 100%;
	height: 100%;
  background: url('../sprite/sprite.png') no-repeat;
  background-size:100%;
  @include sprite__position($bgimg,2208px);
}
</style>
