<template>
	<view>
		这是B组件的数据{{num}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:0
			};
		},
		created() {
			uni.$on('updataNum',num=>{
				this.num += num
			})
		}
	}
</script>

<style>

</style>
