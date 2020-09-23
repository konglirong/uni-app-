<template>
	<view>
		<button type="default" @click="addNum">修改b组件的数据</button>
		<view>
		    <uni-calendar 
		    :insert="true"
		    :lunar="true" 
		    :start-date="'2019-3-2'"
		    :end-date="'2019-5-20'"
		    @change="change"
		     />
		</view>
	</view>
</template>

<script>
	import uniCalendar from '@/components/uni-calendar/uni-calendar.vue'
	export default {
		components: {
		    uniCalendar
		},
		data() {
			return {
				
			};
		},
		methods:{
			addNum(){
				uni.$emit('updataNum',10)
			},
			change(e) {
			    console.log(e);
			}
		}
	}
</script>

<style>

</style>
