<template>
	<view>
		<text @click="addNum">修改b组件的数据</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num: 0
			};
		},
		methods:{
			addNum(){
				uni.$emit('updateNum',10)
			}
		}
	}
</script>

<style>

</style>
