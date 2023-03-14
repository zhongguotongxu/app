<template>
	<view>
		
		<view class="">
			nihao
		</view>
		<view class="" v-for="(item,index) in dataList" :key="index">
		<view class="" :style="{'background':item.flag == 3 ? '#00b47c':(item.flag == 1) ?'#007ce6':(item.flag == 2) ?'#da3f3f': ''}">
				<view class="" style="font-size: 22px;color: #fff;">{{item.name}}</view>
				<view class="" style="color: #fff;">空气质量</view>
		</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dataList:[
					  {
					    flag: "1",
					    data: [35,36,31,33,13,34],
						name:'小刚',
					  },
					  {
					    flag: "2",
					    data: [18,27,21,24,6,28],
						name:'小明',
					  },
					  {
					    flag: "3",
					    data: [18,27,21,24,6,28],
					  	name:'小红',
					  }
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
