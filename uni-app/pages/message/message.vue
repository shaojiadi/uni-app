<template>
	<view>
		<button @click="getInfo">发送get请求</button>
		<button @click="setStorages">存储数据</button>
		<button @click="getStorages">获取数据</button>
		<button @click="removeStorages">移除数据</button>
		<button @click="chooseImg">上传图片</button>
		<image v-for="(item,index) in imgArr" :key="index" mode="aspectFill" :src="item" @click="previewImg"></image>
		<!-- #ifdef H5 -->
			<view>只在h5中可见</view>
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN -->
			<view>只在小程序中可见</view>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data(){
			return {
				imgArr: []
			}
		},
		methods:{
			getInfo(){
				uni.request({
					url: 'http://localhost:8000/',
					success(res){
						console.log(res)
					}
				})
			},
			setStorages(){
				uni.setStorage({
					key: 'id',
					data: 80,
					success(){
						console.log('存储成功')
					}
				})
			},
			getStorages(){
				uni.getStorage({
					key: 'id',
					success(res){
						console.log(`获取成功${res.data}`)
					}
				})
			},
			removeStorages(){
				uni.removeStorage({
					key: 'id',
					success(){
						console.log('删除成功')
					}
				})
			},
			chooseImg(){
				uni.chooseImage({
					count: 5,
					success:(res)=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			previewImg(current){
				uni.previewImage({
				   current,
				   urls: this.imgArr,
				   loop: true,
				   indicator: Number
				});
			}
		},
		onLoad() {
			// #ifdef H5
				console.log('h5打印')
			// #endif
			// #ifdef MP-WEIXIN
				console.log('小程序打印')
			// #endif
		}
	}
</script>

<style>
	/* #ifdef H5 */
		view {
			color: #007AFF;	
		}
	/* #endif */
	
	/* #ifdef MP-WEIXIN */
		view {
			color: #795DA3;
		}
	/* #endif */
</style>
