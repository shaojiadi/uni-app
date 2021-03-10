<template>
	<view>
		<view class="redirec">跳转</view>
		<navigator url="/pages/detail/detail?id=80&age=18">跳转至详情页</navigator>   <!--无法跳转☞tabBar页面-->
		<navigator url="/pages/index/index" open-type="switchTab">跳转至首页</navigator>   
		<navigator url="/pages/detail/detail" open-type="redirect">跳转至详情页</navigator>      <!--关闭当前页面并跳转，无返回-->
		<button @click="goUrl(1)">跳转至详情页</button>
		<button @click="goUrl(2)">跳转至首页</button>
		<button @click="goUrl(3)">跳转至详情页并关闭当前页面</button>
		<test v-if="flag"></test>
		<button @click="flag=!flag">组件按钮</button>
		<a></a>
		<b></b>
		<view>
		<uni-calendar 
			:insert="true"
			:lunar="true" 
			@change="change"
			 />
		</view>
	</view>
</template>

<script>
import test from '../../components/test.vue'
import a from '../../components/a.vue'
import b from '../../components/b.vue'
	export default {
		data(){
			return {
				flag: true
			}
		},
		methods:{
			goUrl(type){
				if(type==1){
					uni.navigateTo({
					    url: '/pages/detail/detail'
					});
				}else if(type==2){
					uni.switchTab({
					    url: '/pages/index/index'
					});
				}else if(type==3){
					uni.redirectTo({
					    url: '/pages/detail/detail'
					});
				}
				
			},
			change(e){
				console.log(e)
			}
		},
		components:{
			test,
			a,
			b
		}
	}
</script>

<style>
	.redirec {
		font-size: 20px;
		text-align: center;
	}
</style>
