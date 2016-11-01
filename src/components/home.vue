<template>
<div class="page">
	<div class="addoil"></div>
	<div class="gotext" @click="go" v-if="!show"></div>
	<div class="bg-grey" v-if="show">
		<div class="intro"></div>
	</div>
</div>
</template>
<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    go() {
      this.show = true;
    },
  },
};
</script>
<style lang='scss' scoped>
@import '../../static/mixins/_sprite.scss';
.page{
  height: 100%;
  width: 100%;
  position: relative;
}
.bg-grey{
	height: 100%;
	width: 100%;
	position: fixed;
	z-index: 10;
	background: rgba(47, 47, 51, 0.9);
}
.addoil{
	position: absolute;
	top: 50px;
	left: 50%;
	transform:translateX(-50%);
	@include sprite($addoil);
}
.gotext{
	position: absolute;
	left: 50%;
	top:50%;
	transform: translate(-50%,-50%);
	@include sprite($gotext);
	animation: shake 1s infinite;
}
@keyframes shake {
    0%, 100% {
        transform:translate(-50%,-50%) rotate(0deg);
    }
    10%,
    30%,
    50%,
    70%,
    90% {
        transform:translate(-50%,-50%) rotate(3deg);
    }
    20%,
    40%,
    60%,
    80% {
        transform:translate(-50%,-50%) rotate(-3deg);
    }
}
.intro{
	animation: move 4s forwards;
	position: absolute;
	left: 50%;
	top:-50%;
	transform: translate(-50%,-50%);
	@include sprite($intro);
	border-radius: 10px;
	z-index: 40;
}
@keyframes move {
  from { top: -50%;}
  to   { top: 50%;}
}
</style>