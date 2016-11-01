<template>
<div class="page">
	<div class="addoil"></div>
	<div class="gotext" @click="go" v-if="!show"></div>
	<div class="bg-grey" v-if="show">
		<div class="intro">
      <div class="intro_info">
        <p>此技术由木犀团队</p>
        <a>www.muxistudio.com</a>
        <p>全面提供</p>
        <p>想要享受更多的华师便利？</p>
        <p>点击下载华师匣子</p>
        <a>ccnubox.muxixyz.com</a>
        <p>从成为匣客开始</p>
      </div>
    </div>
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
@import '../../static/common.scss';
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
  width: 100%;
  position: absolute;
  top:0;
  left: 0;
  height: 13%;
	background: url('../sprite/sprite.png') no-repeat;
  @include _sprite($addoil,305px);
}
.gotext{
  width: 50%;
  height: 20%;
	position: absolute;
	left: 50%;
	top:50%;
	transform: translate(-50%,-50%);
  background: url('../sprite/sprite.png');
  @include _sprite($gotext,524px);
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
  width: 300px;
  height: 40%;
	left: 50%;
	top:-50%;
	transform: translate(-50%,-50%);
	@include _sprite($intro,1358px);
	border-radius: 10px;
	z-index: 40;
}
.intro_info{
  line-height: 20px;
  font-family:zcool;
  letter-spacing: 2px;
  text-align: center;

  p{
    color:#2072b8;
  }
  a{
    color: #ff7200;
  }
}
@keyframes move {
  from { top: -50%;}
  to   { top: 50%;}
}
</style>