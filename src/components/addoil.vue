<template>
<div class="page">
	<div class="top">
		<div class="top_addoil"></div>
	</div>
	<div class="board">
		<div class="text">
			<p id="content">{{ this.content }}</p>
		</div>
		<div class="button">
			<div class="button_wraper">
				<button class="button_red" @click='getanother'>再来一个</button>
				<button class="button_green" @click='copy'>复制</button>
			</div>
		</div>
	</div>
	<div class="bottom">
		<div class="shift"><img src="../images/shift.gif"></div>
		<div class="ccnubox">千万不要向左滑</div>
	</div>
</div>
</template>
<script>
import request from 'superagent';

export default{
  data() {
    return {
      content: '',
    };
  },
  props: {
    propdata: {
      type: String,
    },
  },
  created() {
  	console.log(this);
  	this.content = this.propdata;
  	var startX,startY,endX,endY;
  	document.addEventListener('touchstart', (ev)=>{
        startX = ev.touches[0].pageX;
        startY = ev.touches[0].pageY;  
    }, false);
    document.addEventListener('touchend', (ev)=>{
        endX = ev.changedTouches[0].pageX;
        endY = ev.changedTouches[0].pageY;
        getDeg();
    },false);
    var getDeg=()=>{
    	var x,y;
        x=endX - startX;
        y=startY - endY;
        var deg=Math.atan2(y, x)*180/Math.PI,
        result;
        if(deg>=45&&deg<135) {
            result=1;
        } else if(deg>=135 || deg<-135) {
            result=2;
        } else if(deg>=-135&&deg<-45) {
            result=3;
        } else if(deg>=-45&&deg<45){
            result=4;
        }
        switching(result);
    }
    var switching=(result)=>{
        if (result==2) {
        	this.$parent.$parent.ccnubox();
        }
    }
  },
  methods: {
    getanother() {
      request
        .get('/result')
        .end((err, res) => {
          if (err) throw err;
          this.content = res.body;
        });
    },
    copy() {
      var create = document.createElement("input");
      create.setAttribute("value", this.content);
      document.body.appendChild(create);
      create.select();
      document.execCommand('copy');
      document.body.removeChild(create);
    },
  },
};
</script>
<style lang='scss' scoped>
@import '../../static/common.scss';
.page{
	height: 100%;
	width: 100%;
	display: -webkit-flex;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}
.top{
	height: 15%;
}
.top_addoil{
	width: 100%;
	position: absolute;
	top:0;
	left: 0;
	height: 13%;
	background: url('../sprite/sprite.png') no-repeat;
	@include _sprite($article,305px);
}
.board{
	width: 100%;
	height: 100%;
	position: absolute;
	left: 50%;
	top:50%;
	transform: translate(-50%,-50%);
	overflow: hidden;	
	@include _sprite($board,2208px);
}
.text{
	position: absolute;
	height: 50%;
	margin:5% 0;
	padding:0 20%;
	top:20%;
	font-size: calc(1vh + 10px);
	line-height: 25px;
	text-align: left;
	text-overflow: hidden;
	overflow: scroll;
}
.bottom{
	position: absolute;
	bottom: 0px;
}
.shift{
	width: 100%;
	height: 28%;
	text-align: center;
	margin-bottom: 10px;
	img{
		width: 35%;
		height: 100%;
	}
}
.button{
	width: 60%;
	position: absolute;
	left: 50%;
	transform: translate(-50%,0);
	bottom: 16%;
}
.button_wraper{
	width: 100%;
	display: flex;
	justify-content: space-between;
}
button{
	width:45%;
	height: 30px;
	border-radius: 3px;
	border: 0px;
	box-shadow: 0px 5px 5px silver;
	color:white;
	text-shadow: 2px 2px 2px #726c6a;
}
.button_red{
	background-color: #eb4c13;
}
.button_green{
	background-color: #01a669;
}
.bottom{
	height: 10%;
	width: 100%;
	text-align: center;
}
.ccnubox{
	font-size: 16px;
	color: white;
}
</style>