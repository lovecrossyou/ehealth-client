<template>
	<view class="wrapper">
		<view class="title_text">{{titleText}}</view>
		<view class="blue_bar"></view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	props:{
		titleText:String
	}
};
</script>

<style scoped>
.wrapper {
	width:75upx;
	text-align: center;
	margin:50upx 0 30upx 0;
}
.title_text {
	width: 75upx;
	color: #000;
	font-size: 36upx;
	font-weight: 500;
	z-index: 999;
}
.blue_bar {
	width:75upx;
	height:15upx;
	background-color: #476AFF;
	opacity:0.8;
	margin-top: -20upx;
}
</style>
