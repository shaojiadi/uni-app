<template>
	<view>
		<view class="box2" hover-class="box2-active">
			<view class="box"  :hover-start-time="2000"   hover-class="box-active" hover-stop-propagation>详情页</view>
		</view>
		<view>
			<text selectable="true">{{msg}}</text>
		</view>
		<view>
			<text space="nbsp">创建       下周</text>
		</view>
		<view>
			<text space="emsp">创建       下周</text>
		</view>
		<image :src="imgUrl" mode="aspectFill"></image>
		<view>
			<button size="mini" type="primary" plain @click="clickHandle(20,$event)">按钮</button>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return {
				msg: 'hello',
				imgUrl: 'http://destiny001.gitee.io/image/cxk.gif'
			}
		},
		onLoad(options){
			console.log(options)
		},
		methods:{
			clickHandle(num,e){
				console.log(num,e)
			}
		}
	}
</script>

<style>
	.box {
		width: 100px;
		height: 100px;
		background-color: #007AFF;
	}
	.box2 {
		width: 200px;
		height: 200px;
		background-color: #DD524D;
	}
	
	.box2-active {
		background-color: #4CD964;
	}
	.box-active {
		background-color: pink;
	}
	
</style>
