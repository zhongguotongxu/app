<template>
	<view class="">
		<view class="top">
			smartisan
		</view>
		<view class="banner">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" circular>
				<swiper-item v-for="(item,i) in list[0].panelContents" :key="i">
					<view class="swiper-item">
						<image style="border-radius: 20rpx;margin: 10rpx 0rpx 10rpx 20rpx;width: 700rpx;height: 280rpx;" :src="item.productImageBig" mode=" aspectFit"></image>
					</view>
				</swiper-item>

			</swiper>
		</view>
		<view class="" v-for="(item,i) in list" :key="i">

			<view class="index_ad" v-if="item.type==1">
				<view class="index_ad_item" v-for="(ad,i) in item.panelContents" :key="i">
					<image :src="ad.productImageBig" mode="widthFix"></image>
				</view>
			</view>

			<view class="index_hotDtail" v-if="item.type==2">
				<view class="index_hotDtail_menu">
					{{item.name}}
				</view>
				<view class="index_hotDtail_main">

					<view class="index_hotDtail_main_item" v-for="(hotDetal,i) in item.panelContents" :key="i">
						<view class="index_hotDtail_main_item">
							<image :src="hotDetal.productImageBig" mode="widthFix"></image>
							<text>{{hotDetal.productName}}</text>
							<text>{{hotDetal.salePrice}}</text>
						</view>

					</view>
				</view>
			</view>

			<view class="index_product" v-if="item.type==3">
				<view class="index_hotDtail_menu">
					{{item.name}}
				</view>

				<view class="index_product_bigImg" v-for="(bigPic,i) in item.panelContents" :key="i"
					v-if="bigPic.type==2||bigPic.type==3">
					<image :src="bigPic.productImageBig" mode="widthFix"></image>
				</view>

				<view class="index_hotDtail_main">
					<view class="index_hotDtail_main_item" v-for="(smallPic,i) in item.panelContents" :key="i"
						v-if="smallPic.type==0">
						<view class="index_hotDtail_main_item">
							<image :src="smallPic.productImageBig" mode="widthFix"></image>
							<text>{{smallPic.productName}}</text>
							<text>{{smallPic.salePrice}}</text>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="footer">
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list: [],
				// panelContents:[],
			}
		},
		onLoad() {
			this.getData()
		},
		methods: {
			getData() {
				uni.request({
					url: 'http://api.mm2018.com:8090/api/goods/home',
					success: res => {
						console.log(res.data.result)
						this.list = res.data.result
					}
				})
			}
		}
	}
</script>

<style>
	.top {
		width: 750rpx;
		height: 80rpx;
		background: #000;
		line-height: 80rpx;
		text-align: center;
		color: #fff;
	}

	.banner {
		width: 750rpx;
		background: #f5f5f5;
	}

	.banner image {
		width: 100%;
	}

	.index_ad {
		width: 700rpx;
		border: 2rpx solid #dbdbdb;
		margin: 0 auto;
		margin-top: 30rpx;
		border-radius: 10rpx;
		overflow: hidden;
		border-right: 0px;
		border-bottom: 0px;
	}

	.index_ad_item {
		width: 50%;
		float: left;
		border-right: 2rpx solid #dbdbdb;
		box-sizing: border-box;
		border-bottom: 2rpx solid #dbdbdb;
	}

	.index_ad_item image {
		width: 100%;
		display: block;
	}

	.index_hotDtail {
		width: 700rpx;
		margin: 0 auto;
		margin-top: 30rpx;
	}

	.index_hotDtail_menu {
		width: 700rpx;
		font-size: 28rpx;
		font-weight: bold;
		color: #5e5e5e;
	}

	.index_hotDtail_main {
		width: 700rpx;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		overflow: hidden;
	}

	.index_hotDtail_main_item {
		width: 337rpx;
		background: #f2f2f2;
		overflow: hidden;
		border-radius: 10rpx;
		padding-bottom: 10rpx;
		box-sizing: border-box;
		height: auto;
		margin-top: 30rpx;
	}

	.index_hotDtail_main_item image {
		width: 60%;
		display: block;
		margin: 0 auto;
		margin-bottom: 20rpx;
	}

	.index_hotDtail_main_item text {
		display: block;
		text-align: center;
		font-size: 26rpx;
		line-height: 40rpx;
		white-space: nowrap;
		text-overflow: ellipsis;
		overflow: hidden;
	}

	.index_product {
		width: 700rpx;
		height: auto;
		margin: 0 auto;
		overflow: hidden;
		margin-top: 30rpx;
	}

	.index_product_bigImg {
		width: 100%;
		height: auto;
		margin-top: 30rpx;
	}

	.index_product_bigImg image {
		width: 100%;
		display: block;
	}

	.footer {
		width: 100%;
		height: 100rpx;
		background: #000000;
		margin-top: 30rpx;
	}
</style>
