<template>  
	<view class="content">  
		<view class="tit">  
			<swiper class="swiper" indicator-dots indicator-active-color="#fff" circular autoplay>  
				<swiper-item v-for="item in rotation" :key="item.id">  
					<image :src="item.url" class="swiper-item"></image>  
				</swiper-item>  
			</swiper>  
		</view>
		<view class="game">
			<view class="game-itme">
				<a href="https://www.vqs.com/down/106617.html" >
					<image src="../../static/game_picture/tanchishe.png"></image>
					<text>贪吃蛇</text>
				</a>
			</view>
			<view class="game-itme">
				<image src="../../static/icon/课程.png"></image>
				<text>课程学习</text>
			</view>	
			<view class="game-itme">
				<image src="../../static/icon/院校.png"></image>
				<text>院校介绍</text>
			</view>	
			<view class="game-itme">
				<image src="../../static/icon/预约.png"></image>
				<text>预约体检</text>
			</view>	
			<view class="game-itme">
				<image src="../../static/icon/导航图标.png"></image>
				<text>导航图标</text>
			</view>	
			<view class="game-itme">
				<image src="../../static/icon/报到流程.png"></image>
				<text>报到流程</text>
			</view>
			<view class="game-itme">
				<image src="../../static/icon/数据采集-01.png"></image>
				<text>数据采集</text>
			</view>	
			<view class="game-itme">
				<image src="../../static/icon/宿舍管理-分配宿舍.png"></image>
				<text>宿舍管理</text>
			</view>	
		</view>
		<view>
			<text class="message">猜你喜欢</text>
			<view class="msg_box">
				<view class="msg">
					<text class="msg_title">震惊！某高校竟……</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title">重庆高温预警</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title">普通人类能上外太空吗</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title">好看小说分享</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title">2024热播电视剧，你看过哪些？</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title">太奶！你追的漫画更新了！</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title">（广告）原神5.0版本即将上线</text>
					<text class="msg_date">2024-8-18</text>						
				</view>
				<view class="msg">
					<text class="msg_title"></text>
					<text class="msg_date"></text>						
				</view>
				<view class="msg">
					<text class="msg_title"></text>
					<text class="msg_date"></text>						
				</view>
			</view>
		</view> 
	</view>  
</template>  

<script>  
	export default {  
		data() {  
			return {  
				rotation: [  
					{  
						id: 1,  
						url: "../../static/picture/id1.jpg"  
					},  
					{  
						id: 2,  
						url: "../../static/picture/id2.jpg"  
					},  
					{  
						id: 3,  
						url: "../../static/picture/id3.jpg"  
					}  
				]  
			}  
		},  
		methods: {  
			// Define your methods here.  
		}  
	}  
</script>

<style>
	.content {
		display:flex;
		flex-direction: column;
	}
	.tit{
		width:100%;
		height:100%;
		margin-left:0rpx;
	}
	.swiper-item{
		width:100%;
		height:100%;
	}
	.tit image{
		width:100%;
		height:100%;
	}
.game {  
    width: 90%;  
    height: 340rpx;  
    background: #ffffff;  
    margin-left: 7.5%;  
    margin-top: 15rpx;  
    display: flex;  
    flex-wrap: wrap;  
}  
	.game-itme{
		width:155rpx;
		height:155rpx;
		image:10rpx;
	}
	.game-itme image{
		width:90rpx;
		height:90rpx;
		margin-left:20%;
	}
	.game-itme text{
		display :inline-block;
		font-size:30rpx;
		margin-left: 10%;
	}
	/*猜喜欢*/
	.message{
		display:inline-block;
		font-size:27rpx;
		font-weight:bold;
		margin-left:40rpx;
	}
	.msg_box{
		width:95%;
		height: 600rpx;
		background:#ffffff;
		margin-left:2.5%;
		margin-top:15rpx;
		display:flex;
		flex-wrap:wrap;
	}
	.msg{
		width:100%;
		height:90rpx;
		border-bottom:solid #cccccc 1rpx;
	}
	.msg_title{
		font-size: 30rpx;
		line-height: 90rpx;
		margin-left:20rpx;
		font-weight: bold;
		margin-top:20rpx;
	}
	.msg_date{
		display: inline-block;
		float:right;
		font-size: 25rpx;
		margin-top:30rpx;
		margin-right: 20rpx;
	}
</style>
