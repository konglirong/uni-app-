<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title" selectable>{{title}}</text>
		</view>
		<view class="list-item" v-for="item in list">
			{{item}}
		</view>
		<button type="default" @click="pullDown">下拉刷新</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello uni-app',
				list:['aaa','bbb','ccc','ddd','mmm','yyy']
			}
		},
		onPullDownRefresh(){
			console.log('下拉刷新')
			this.list = ['qq','ee','tt','hh','gg','yyy']
			//停止下拉刷新
			setTimeout(()=>{
				uni.stopPullDownRefresh()
			},2000)
		},
		onReachBottom() {
			console.log('页面触底了')
			this.list.push(123,46)
		},
		//页面加载了
		onLoad(option) {
			console.log(option)
		},
		onShow() {
			console.log('show')
		},
		onReady() {
			console.log('ready')
		},
		onHide() {
			console.log('hide')
		},
		methods: {
			pullDown(){
				uni.startPullDownRefresh()
			},
			 
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	.list-item{
		height: 100px;
		line-height: 100px;
	}
</style>
