<template>  
	<view>  
		<view class="content">  
			<view class="name_box">  
				<view class="name" v-for="(item, index) in chatList" :key="index" @click="toChat()">  
					<text class="name_title">{{ item.title }}</text>  
					<text class="name_date">{{ item.date }}</text>						  
				</view>  
			</view>  
		</view>  
	</view>  
</template>  

<script>  
	export default {  
		data() {  
			return {  
				chatList: [  
					{ title: '1', date: '2024-8-18' },  
					{ title: '2', date: '2024-8-18' },  
					{ title: '3', date: '2024-8-18' },  
					{ title: '4', date: '2024-8-18' },  
					{ title: '5', date: '2024-8-18' },  
					{ title: '6', date: '2024-8-18' },  
					{ title: '7', date: '2024-8-18' },  
					{ title: '8', date: '2024-8-18' },  
				]  
			}  
		},  
		methods: {  
			/*跳转*/  
			toChat() {  
				uni.navigateTo({  
					url: "/pages/chat/chat"  
				})  
			}  
		}  
	}  
</script>

<style>
	.name{
		width:100%;
		height:90rpx;
		border-bottom:solid #cccccc 1rpx;
	}
	.name_title{
		font-size: 30rpx;
		line-height: 90rpx;
		margin-left:20rpx;
		font-weight: bold;
		margin-top:20rpx;
	}
	.name_date{
		display: inline-block;
		float:right;
		font-size: 25rpx;
		margin-top:30rpx;
		margin-right: 20rpx;
	}
</style>