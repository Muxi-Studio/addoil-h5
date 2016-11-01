<template>
<div class="page">
	<div class="top">
		<div class="top_addoil"></div>
	</div>
	<div class="board">
		<div class="text">
			<p>WxNotificationCenter - 微信小程序通知广播模式类, 降低小程序开发的耦合度。 类 iOS 中的 NSNotificationCenter 模式 作用 增加页面间传值方式 减少页面之间的耦合度WxNotificationCenter - 微信小程序通知广播模式类, 降低小程序开发的耦合度。 类 iOS 中的 NSNotificationCenter 模式 作用 增加页面间传值方式 减少页面之间的耦合度WxNotificationCenter - 微信小程序通知广播模式类, 降低小程序开发的耦合度。 类 iOS 中的 NSNotificationCenter 模式 作用 增加页面间传值方式 减少页面之间的耦合度</p>
		</div>
		<div class="button">
			<div class="button_wraper">
				<button class="button_red">再来一个</button>
				<button class="button_green">复制</button>
			</div>
		</div>
	</div>
	<div class="bottom">
		<div></div>
		<div class="ccnubox">千万不要向左滑</div>
	</div>
</div>
</template>
<style lang='scss' scoped>
@import '../../static/mixins/_sprite.scss';
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
	margin:25px auto;
	@include sprite($article);
}
.board{
	width: 100%;
	position: relative;
	height: 75%;
	margin:0 auto;
	@include sprite($board);
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}
.text{
	height: 80%;
	padding:0 80px;
	padding-top: 180px;
	font-size: 50px;
	text-align: left;
	line-height: 100px;
	overflow: scroll;
}
.button{
	width: calc(100% - 200px);
	margin:0 100px;
	height: 20%;
}
.button_wraper{
	width: 100%;
	margin-top: 50px;
	display: flex;
	justify-content: space-between;
}
button{
	width:45%;
	height: 130px;
	font-size: 60px;
	border-radius: 10px;
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
	font-size: 50px;
	color: white;
}
</style>