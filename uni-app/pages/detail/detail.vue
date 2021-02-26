<template>
	<view>
		<view class="box2" hover-class="box2-active">
			<view class="box"  :hover-start-time="2000"   hover-class="box-active" hover-stop-propagation>详情页</view>
		</view>
		<view>
			<text selectable="true">武动乾坤</text>
		</view>
		<view>
			<text space="nbsp">创建       下周</text>
		</view>
		<view>
			<text space="emsp">创建       下周</text>
		</view>
		<image src="http://destiny001.gitee.io/image/cxk.gif" mode="aspectFill"></image>
		<button size="mini" type="primary" plain>按钮</button>
	</view>
</template>

<script>
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
