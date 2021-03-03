<template>
	<view>
		<button @click="getInfo">发送get请求</button>
	</view>
</template>

<script>
	export default {
		data(){
			return {
				
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
			}
		}
		
	}
</script>

<style>
</style>
