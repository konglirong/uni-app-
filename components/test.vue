<template>
	<view class="wrapper">
		<view>这是一个组件</view>
		<button type="default" @click="clickEvent()">传值</button>
	</view>
</template>

<script>
	export default{
		data(){
			return {
				num:9999
			}
		},
		methods:{
			clickEvent(){
				console.log(78999)
				this.$emit('getNum',this.num)
			}
		},
		beforeCreate() {
			//数据和页面都没有初始化完成
			console.log('实例已经开始初始化了')
		},
		created() {
			//可以拿到数据和方法
			console.log('实例已经初始化完成')
		},
		beforeMount() {
			//组件还没有渲染到页面上
			console.log('beforeMount')
		},
		mounted() {
			//可以拿到组件,已经渲染了，操作dom
			console.log('mounted')
		},
		beforeUpdate() {
			console.log('beforeUpdate')
		},
		updated() {
			console.log('updated')
		},
		beforeDestroy() {
			console.log('beforeDestroy')
		},
		destroyed() {
			console.log('destroyed')
		}
	}
</script>

<style>
</style>
