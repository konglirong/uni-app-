<template>
	<view>
		<!-- #ifdef  MP-WEIXIN -->
		<text>购物车</text>
		<!-- #endif -->
		<button type="default" @click="imgUp">图片上传</button>
		<image v-for="item in imgArr" @click="preview(item)" :src="item"></image>
		<navigator url="../uni-style/uni-style" open-type="redirect">页面跳转</navigator>
		<navigator url="../index/index" open-type="switchTab">首页</navigator>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[]
			}
		},
		methods: {
			imgUp(){
				uni.chooseImage({
					count:5,
					success:res=>{
						console.log(res.tempFilePaths)
						this.imgArr = res.tempFilePaths
					}
				})
			},
			preview(current){
				uni.previewImage({
					current,
					urls:this.imgArr,
					loop:true,
					indicator:"number"
				})
			}
		}
	}
</script>

<style>

</style>
