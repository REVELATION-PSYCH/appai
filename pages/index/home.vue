<template>
	<view class="container">
		<image class="image" src="/static/home.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="text-area">
			<text class="title">{{text2}}</text>
		</view>
		 <view class="circle-buttons-row">
		    <button class="circle-button">AI生理检测</button>
		    <button class="circle-button">AI中医检测</button>
		    
		  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Beina',
				text2: '欢迎使用宜诊聊'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.image {
		height: 250rpx;
		width: 350rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
		border-radius: 10%;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	
	
	.circle-buttons-row {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  margin-top: 20px;
	
	}
	
	.circle-button {
	  width: 130px;
	  height: 130px;
	  border-radius: 50%; /* make it circular */
	  background-color: #7737FE;
	  color: white;
	  font-size: 15px;
	  text-align: center;
	  line-height: 130px; /* vertically center the text */
	  border: none;
	    margin: 0 10px; /* 10px left and right margin */
	}
</style>
