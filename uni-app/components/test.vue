<template>
	<view id="myView">
		test组件{{num}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:3,
				setId: null
			};
		},
		//组件的生命周期
		beforeCreate(){
			console.log('实例已经开始初始化')
			console.log(this.num)  //undefined
		},
		created(){
			console.log('create',this.num)  //实例化完成，已经有数据 3
			// this.setId = setInterval(()=>{
			// 	console.log('定时器运行')
			// },1000)
		}, 
		beforeMount(){
			// console.log('beforemount',document.getElementById('myView'))   //null,还没有渲染到页面上
		},
		mounted(){
			// console.log('mounted',document.getElementById('myView'))  //已经渲染到dom
		},
		destroyed() {
			// clearInterval(this.setId)
		}
	}
</script>

<style>

</style>
