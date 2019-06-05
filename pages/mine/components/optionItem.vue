<template>
	<view class="wrapper">
		<image :src="itemImg" mode="" class="item_img"></image>
		<view class="main_text">{{mainText}}</view>
		<image src="../../static/mine/icon_arrow_right@2x.png" class="next_img"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {};
		},
		methods: {},
		props:{
			itemImg:String,
			mainText:String
		}
	};
</script>

<style scoped>
	.wrapper{
		width: 100%;
		height: 120upx;
		background-color: #fff;
		border-bottom: 1upx solid #E3E3E3;
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.item_img{
		width: 46upx;
		height: 46upx;
		margin-right: 25upx;
	}
	.main_text{
		color: #333333;
		font-size: 32upx;
		flex: 1;
	}
	.next_img{
		width: 20upx;
		height: 34upx;
	}
</style>
