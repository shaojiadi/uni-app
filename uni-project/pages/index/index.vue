<template>
	<view >
		<swiper class="swiper" indicator-dots autoplay :interval="2000" :duration="500">
			<swiper-item v-for="(item,index) in swipers" :key="index">
				<image :src="item.imgUrl" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
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
</style>
