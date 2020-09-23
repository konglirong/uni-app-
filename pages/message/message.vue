<template>
	<view>
		<text>网络请求</text>
		<button type="default" @click="getData">网络请求</button>
		<button type="default" @click="setStorage">存储数据</button>
		<button type="default" @click="getStorage">获取存储数据</button>
		<button type="default" @click="removeStorage">移除数据</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			getData(){
				uni.request({
					url:"../../static/test.json",
					success(res) {
						console.log(res)
					}
				})
			},
			//储存数据
			setStorage(){
				uni.setStorage({
					key:"id",
					data:{name:"klr",age:18},
					success() {
						console.log('成功')
					}
				})
			},
			//获取数据
			getStorage(){
				uni.getStorage({
					key:"id",
					success(res) {
						console.log('获取成功',res)
					}
				})
			},
			//移除数据
			removeStorage(){
				uni.removeStorage({
					key:'id',
					success(){
						console.log('移除成功')
					}
				})
			}
		}
	}
</script>

<style>

</style>
