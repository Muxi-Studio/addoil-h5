<template>
	<div class="container">
		<div class="main-top">
			<div class="left">
					<img src="../images/logo.jpg" alt="logo" class="logo">
					<img src="../images/light.png" alt="light" class="light">
					<img src="../images/title.png" alt="title" class="title">
					<img src="../images/contents-c.png" alt="" class="content-c">
					<img src="../images/contents-m.png" alt="" class="content-m">
					<a href="javascript:void(0)" class="btn btn-android btn-c" id="btn">Android版下载</a>

					<a href="http://www.wandoujia.com/apps/net.muxi.huashiapp" class="btn btn-android btn-m">Android版下载</a>

					<a href="javascript:void(0)" class="btn btn-ios">iPhone版打磨中</a>
			</div>
			<div class="right">
				<img src="../images/phone.png" alt="phone" class="phone">
			</div>
		</div>
		<div class="main-center">
			<div class="bg x1"></div>
			<div class="bg x2"></div>
			<div class="bg x3"></div>
		</div>
	</div>
</template>
<style lang='scss'>
$background-color: #4a90e8;
$footer-color: #fec300;
$button-color: #ffd14f;

html,body{
	width: 100%;
	height: 100%;
}
.container {
	width: 100%;
	height: 100%;
  background: url('../images/cubes.png');
  background-color: $background-color;
  font: 14px "MicrosoftYaHei Bold", Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  position:relative;
}
a{
	text-decoration: none;
}


	.container{
		z-index: 10;
		max-width: 45rem;
		margin: 0 auto;
		text-align: center;
		min-height: 100%;
		position: relative;
		.main-top{
			img{
				display:block;
				margin: 0 auto;
			}
			.left{
				padding-top: 60px;
				.logo{
					width: 5em;
					height:5em;
				}
				.light{
					z-index: -1;
					width: 12em;
					margin-top: -120px;
					position:relative;
					animation: 9.5s linear 0s normal none infinite rotate;
					-webkit-animation:9.5s linear 0s normal none infinite rotate;
					-moz-animation:9.5s linear 0s normal none infinite rotate;
				}
				.title{
					margin-top: -20px;
					width: 80%;
				}
				.content-c{
					display: none;
				}
				.content-m{
					width: 90%;
					margin: 10% auto;
				}
				.btn{
					width: 60%;
				    line-height: 50px;
				    text-align: center;
				    height: 50px;
				    font-size: 22px;
				    text-decoration: none;
				    letter-spacing: .07em;
				    border-radius: 5px;
				    display: block;
				}
				.btn-ios{
					background-color:#c9c9c9;
					color: #fff;
					border-bottom: 4px solid #616161;
					cursor: not-allowed;
					margin: 0 auto;
				}
				.btn-android{
				    cursor: pointer;
				    background-color:$button-color;
				    color: #fff;
				    border-bottom: 4px solid #ff6d33;
					margin: 5% auto;
				    &:active,&:hover{
				    	position: relative;
				    	top: 1px;
				    	border-bottom: 0;
				    }
				}
				.btn-c{
					display: none;
				}
			}
			.right{
				display: none;
			}
		}
		.main-center,.main-bottom{
			display: none;
		}
		@keyframes rotate{
			from{transform:rotate(0deg)}
			to{transform:rotate(360deg)}
		}
		@-webkit-keyframes rotate{
			from{-webkit-transform:rotate(0deg)}
			to{-webkit-transform:rotate(360deg)}
		}
		@-moz-keyframes rotate{
			from{-moz-transform:rotate(0deg)}
			to{-moz-transform:rotate(360deg)}
		}

	}
	footer{
		position: absolute;
		bottom: 0;
		left: 0;
		background-color:$footer-color;
		text-align: center;
		width: 100%;
		p,a{
			display: inline-block;
			height: 1.6em;
			line-height: 1.6em;
			color: #fff;
		}
		a{
			cursor: pointer;
			margin:0 .5em;
		}
		a:hover{
			color: $background-color;
		}
	}
	.erwei{
		display: none;
	}

#mask{
	position: absolute;
    left: 0;
    top: 0;
    background: rgba(0, 0, 0, 0.5);
    z-index: 2;
}
	
</style>	
<script>
  window.onload = function(){
    let btn = document.getElementById("btn");
		let erwei = document.getElementById("erwei")
		function displayNew(){
			let sHeight = document.documentElement.scrollHeight
			let sWidth = document.documentElement.scrollWidth
			//可视区域
			let wHeight = document.documentElement.clientHeight

			let mask = document.createElement('div')
			mask.id = "mask";
			mask.style.height = sHeight + "px"
			mask.style.width = sWidth + "px"
			document.body.appendChild(mask)
			
			//关闭
			let close = document.getElementById('close')
			mask.onclick = close.onclick = function(){
				document.body.removeChild(mask)
				erwei.style.display = 'none'
			}
		}
		
		// btn.onclick = function(){
		// 	erwei.style.display = 'block'
		// 	displayNew()
		// }
	}
</script>