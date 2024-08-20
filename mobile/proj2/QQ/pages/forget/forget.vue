<template>
	<view>
		<view class="content">
			<image class="logo" src="../../static/logo/logo.jpg"></image>
			<view class="load_box">
				<input type="text" placeholder="      输入手机号">
			</view>
			<view class="password_box">
				<input type="safe-password" password placeholder="         输入密码">
			</view>
			<view class="repass_box">
				<input type="safe-password" password placeholder="  再次确认你的密码">
			</view>
			<view class="auth_box">
				<input type="text" placeholder="      输入验证码">
			</view>
			<button class="get_box" >获取验证码</button>
			<button class="btn" @click="toLogin">确认注册</button>
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
			toLogin:function(){
				uni.navigateTo({
					url:"/pages/login/login"
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
		margin-top:10%;
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
	.auth_box{
		width:70%;
		height:60rpx;
		margin-top:5%;
		margin-left: 15%;
		background:#ffffff;
		box-shadow:4px 3px #b6b6b6 ;
		border-radius:30px;
	}
	.auth_box input{
		margin-top:2%;
		margin-left: 23%;
		color: #000000;
	}
	.get_box{
		width:40%;
		height:60rpx;
		margin-top:5%;
		margin-left: 30%;
		background: rgba(13, 180, 226, 0.8);
		border-radius:10px;
		font-size:25rpx;
		color:#ffffff;
	}
	.password_box{
		width:70%;
		height:60rpx;
		margin-top:5%;
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
	.repass_box{
		width:70%;
		height:60rpx;
		margin-top:5%;
		margin-left: 15%;
		background:#ffffff;
		box-shadow:4px 3px #b6b6b6 ;
		border-radius:30px;
	}
	.repass_box input{
		margin-top:2%;
		margin-left: 23%;
		color: #000000;
		font-size: 15px;
	}
	.btn{
		width:40%;
		height:60rpx;
		background:rgba(13, 180, 226, 0.8);
		border-radius:10px;
		font-size:25rpx;
		color:#ffffff;
		margin-top:7%;
	}
</style>
