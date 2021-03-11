<template>
	<view >
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers: []
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
				const res = await this.$myRequest({
					url: '/getLunbo'
				})
				console.log(res)
			}
		}
	}
</script>

<style>
	
</style>
