<template>
<div class="page">
	<div class="intro"></div>
</div>
</template>
<style lang='scss' scoped>
@import '../../static/mixins/_sprite.scss';
.page{
  height: 100%;
  width: 100%;
  position: relative;
  z-index: 10;
  background: rgba(47, 47, 51, 0.9);
}
.intro{
	animation: move 4s forwards;
	position: absolute;
	left: 50%;
	top:-50%;
	transform: translate(-50%,-50%);
	@include sprite($intro);
	border-radius: 10px;
}
@keyframes move {
  from { top: -50%;}
  to   { top: 50%;}
}
</style>