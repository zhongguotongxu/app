<template>
	<view :class="test" :style="{color:color,fontSize:fontSize+'rpx'}">
		hello uni-app 你好吗
	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				test:"hello",
				color:"white",
				fontSize:40
			}
		},
		methods: {
			
		}
	}
</script>

<style>
@import url("../../common/hello.css");
</style>
