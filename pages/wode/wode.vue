<template>
	<view class="wrapper">
		<view class="box" hover-class="box-active">测试</view>
		<image class="logo" src="http://destiny001.gitee.io/image/cxk.gif" mode="aspectFill"></image>
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<test @getNum="getNumP" />
		<text>{{num}}</text>
		<text-a></text-a>
		<text-b>{{num}}</text-b>
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	import testA from '../../components/a.vue'
	import testB from '../../components/b.vue'
	export default {
		components:{
			test,
			"text-a":testA,
			"text-b":testB
		},
		data() {
			return {
				num:0
			}
		},
		methods: {
			getNumP(num){
				this.num = num
				console.log(num)
			}
		}
	}
</script>

<style>
.box{
	width: 100%;
	height: 200px;
	background: #808080;
}
.box-active{
	background: #007AFF;
}
</style>
