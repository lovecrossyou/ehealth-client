<template>
	<view class="wrapper">
		<!-- 头部背景 -->
		<view class="top_bg">
			<view class="topic_title">北京西城区自行出台康养养老规范，能否作为行业典范进行实行？</view>
			<view class="bottom_area">
				<view class="discussion_num">1.5万人讨论</view>
				<view class="attention_btn">+ 关注</view>
			</view>
		</view>
		<!-- 讨论文章 -->
		<view class="discussion_article">
			<view class="article_content">
				<view class="publisher_info">
					<image src="http://img2.imgtn.bdimg.com/it/u=1961142815,2698003411&fm=26&gp=0.jpg" mode="aspectFill" class="publisher_header_img"></image>
					<view class="publisher_presentation">
						<view class="publisher_name">牛牧</view>
						<view class="publisher_corporation">北京富腾投资集团有限公司</view>
					</view>
					<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
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
.top_bg {
	width: 100%;
	height: 430upx;
	background: linear-gradient(131deg, rgba(57, 160, 255, 1), rgba(132, 233, 255, 1));
	padding: 36upx 36upx 0 36upx;
	box-sizing: border-box;
}
.topic_title {
	color: #fff;
	font-size: 32upx;
	font-weight: bold;
	line-height: 44upx;
	margin-top: 130upx;
}
.bottom_area {
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	margin-top: 30upx;
}
.discussion_num {
	color: #ffffff;
	font-size: 26upx;
}
.attention_btn {
	width: 111upx;
	height: 49upx;
	background: #5871FE;
	border-radius: 4upx;
	color: #fff;
	font-size: 26upx;
	text-align: center;
	line-height: 49upx;
}
.discussion_article{
	width: 100%;
	background-color: #fff;
	border-radius: 20upx 20upx 0 0;
	margin-top: -50upx;
	padding: 50upx 31upx 30upx 31upx;
	box-sizing: border-box;
}
.article_content{
	width: 100%;
}
.publisher_info {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
}
.publisher_header_img {
	width: 74upx;
	height: 74upx;
	border-radius: 4upx;
}
.publisher_presentation {
	display: flex;
	flex: 1;
	flex-direction: column;
	margin-left: 26upx;
}
.publisher_name {
	color: #333333;
	font-size: 30upx;
	font-weight: bold;
}
.publisher_corporation {
	color: #999;
	font-size: 24upx;
	margin-top: 5upx;
}
.publish_text {
	width: 100%;
	color: #333;
	font-size: 30upx;
	padding: 0 31upx;
	box-sizing: border-box;
}
.hidden_arrows {
	width: 30upx;
	height: 16upx;
	margin: 10upx 0 0 10upx;
}
</style>
