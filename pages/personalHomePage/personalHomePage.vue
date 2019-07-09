<template>
	<view class="wrapper">
		<!-- 分享 -->
		<view class="share_area">
			<image src="" class="share_icon"></image>
			<image src="http://qnimage.xiteng.com/share@2x.png" class="share_icon"></image>
		</view>
		<!-- 头部背景 -->
		<view class="blue_bg">
			<!-- 个签 & 头像 -->
			<view class="center_cont">
				<view class="signature_text">生命的全部的意义在于无穷地探索尚未知道的东西。</view>
				<image src="http://img2.imgtn.bdimg.com/it/u=3475306759,3888235577&fm=26&gp=0.jpg" mode="aspectFill" class="header_img"></image>
			</view>
			<!-- 名片 -->
			<view class="business_card">
				<view class="">
					<view>扎克伯格</view>
					<view>产品经理</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.blue_bg {
	width: 100%;
	height: 470upx;
	background: linear-gradient(180deg, #5871fe, #fff);
	padding: 31upx;
	box-sizing: border-box;
}
.share_area {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
	padding: 31upx;
	box-sizing: border-box;
	background-color: #5871FE;
}
.share_icon {
	width: 34upx;
	height: 32upx;
}
.center_cont {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	margin-top: 30upx;
}
.signature_text{
	width: 445upx;
	color: #FFFFFF;
	font-size: 28upx;
}
.header_img{
	width:160upx;
	height:160upx;
	border-radius:50%;
}
.business_card{
	width:690upx;
	height:330upx;
	background:#fff;
	box-shadow:0px 1px 20px 0px rgba(18,53,114,0.14);
	border-radius:10upx;
	margin-top: 50upx;
}
</style>
