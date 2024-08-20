<template>
	<view class="content">
		<image class="logo" src="../../static/logo/logo.jpg"></image>
		<view class="load_box">
			<input type="text" placeholder="QQ号/手机号/邮箱">
		</view>
		<view class="password_box">
			<input type="safe-password" password placeholder="         输入密码">
		</view>
		<button class="btn" @click="toIndex()">登录</button>
		<view class="down_box">
			<text class="forget" @click="toForget()">忘记密码</text>
			<text class="register" @click="toRegister()">用户注册</text>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			/*跳转*/
			toForget:function(){
				uni.navigateTo({
					url:"/pages/forget/forget"
				})
			},
			toIndex:function(){
				uni.switchTab({
					url:"/pages/index/index"
				})
			},
			toRegister:function(){
				uni.navigateTo({
					url:"/pages/register/register"
				})
			}
		}
	}
</script>

<style>
.content{
	display:flex;/*弹性布局*/
	flex-direction:column;
}
.logo {
	width:50%;
	height:200rpx;
	margin-top: 20%;
	margin-left:25%;
}
.load_box{
	width:70%;
	height:60rpx;
	margin-top:15%;
	margin-left: 15%;
	background:#ffffff;
	box-shadow:4px 3px #b6b6b6 ;
	border-radius:30px;
}
.load_box input{
	margin-top:2%;
	margin-left: 23%;
	color: #000000;
}
.password_box{
	width:70%;
	height:60rpx;
	margin-top:10%;
	margin-left: 15%;
	background:#ffffff;
	box-shadow:4px 3px #b6b6b6 ;
	border-radius:30px;
}
.password_box input{
	margin-top:2%;
	margin-left: 23%;
	color: #000000;
	font-size: 15px;
}
.down_box{
	width:60%;
	height:60rpx;
	margin-top:45%;
	margin-left: 20%;
	background:#ffffff;
}
.forget{
	margin-top:2%;
	float:left;
	color: #000000;
	font-size: 13px;
}
.register{
	margin-top:2%;
	float:right;
	color: #000000;
	font-size: 13px;
}
.btn{
	width:40%;
	height:60rpx;
	background:rgba(13, 180, 226, 0.8);
	border-radius:10px;
	font-size:25rpx;
	color:#ffffff;
	margin-top:10%;
}
</style>
