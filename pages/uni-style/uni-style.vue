<template>
	<view>
		<view class="word">
			{{msg}}
		</view>
		<view class="box1">
			测试
		</view>
		<!-- 引入字体图标 -->
		<view class="iconfont icon-browse"></view>
		<view class="iconfont icon-3column"></view>
		<button type="default" @click="clickHandler">按钮</button>
	</view>
</template>
<script>
	export default{
		data(){
			return {
				msg:"hello klr"
			}
		},
		methods:{
			clickHandler(){
				console.log(12)
			}
		}
	}
</script>
<style lang="scss">
	@import url("./a.css");
.box1{
	width: 375rpx;
	height: 357rpx;
	background: $uni-color-primary;
	font-size: 30rpx;
	color: #fff;
	line-height: 375rpx;
	text-align: center;
}
</style>
