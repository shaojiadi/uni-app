<template>
	<view >
		<swiper class="swiper" indicator-dots autoplay :interval="2000" :duration="500">
			<swiper-item v-for="(item,index) in swipers" :key="index">
				<image :src="item.imgUrl" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
		<!-- 导航栏 -->
		<view class="nav">
			<view class="nav_item">
				<view class="iconfont icon-xiaomi"></view>
				<text>小米上新</text>
			</view>
			<view class="nav_item">
				<view class="iconfont icon-bijiben"></view>
				<text>笔记本</text>
			</view>
			<view class="nav_item">
				<view class="iconfont icon-xingzhuang"></view>
				<text>大家电</text>
			</view>
			<view class="nav_item">
				<view class="iconfont icon-shouji"></view>
				<text>手机</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers: [],
			}
		},
		onLoad() {
			this.getSwiper();
		},
		methods: {
			/* getSwiper(){
				uni.request({
					url: 'http://localhost:8000/getLunbo',
					success: (res) => {
						if(res.data.status !==0 ){
							return uni.showToast({
								title: '获取数据失败'
							})
						}else{
							this.swipers = res.data.message;
						}
					}
				})
			} */
			/* async getSwiper(){
				const res =  await uni.request({
					url: 'http://localhost:8000/getLunbo',
				})
				console.log(res)
			} */
			async getSwiper(){
				const res = await this.$myRequest({     //$myRequest main.js中全局注册
					url: '/getLunbo'
				})
				this.swipers = res.data.message;
				console.log(this.swipers)
			}
		}
	}
</script>

<style lang="scss">
	.swiper {
		width: 750rpx;
		height: 400rpx;
		image {
			width: 100%;
			height: 100%;
		}
	}
	.nav{
		margin-top: 40rpx;
		display: flex;
		.nav_item {
			width: 25%;
			text-align: center;
			margin: 0 auto;
			view {
				width: 100rpx;
				height: 100rpx;
				background: rgba(0,0,0,1);
				border-radius: 60rpx;
				font-size: 40rpx;
				line-height: 100rpx;
				text-align: center;
				color: #fff;
				margin: 0 auto;
			}
			text {
				font-size: 30rpx;
			}
		}
	}
	
</style>
