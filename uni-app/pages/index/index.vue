<template>
	<view class="content">
		<image class="logo" src="/static/tab/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view v-for="(item,index) in userList" :key="index" class="user">
			{{item}}
		</view>
		<view>
			<button type="primary" @click="pullDown">按钮</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				userList: ['小王','小明','小芳','小夏','网名']
			}
		},
		onLoad() {
			console.log('页面加载')
		},
		onShow(){
			console.log('页面显示')
		},
		onReady(){
			console.log('页面初次渲染')
		},
		onHide(){
			console.log('页面隐藏');
		},
		onPullDownRefresh(){
			console.log('触发了下拉刷新');
			setTimeout(()=>{
				uni.stopPullDownRefresh()      //停止当前页面下拉刷新
			},2000)
		},
		onReachBottom(){
			console.log('页面触底');
			this.userList = [...this.userList,...[888,999,111]]
			console.log(this.userList)
		},
		methods: {
			pullDown(){
				uni.startPullDownRefresh()     //开始下拉刷新
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	.user {
		margin: 100px;
	}
</style>
