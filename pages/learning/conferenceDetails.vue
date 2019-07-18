<template>
	<view class="wrapper">
		<!-- 头部banner -->
		<image src="http://qnimage.xiteng.com/tu.png" mode="aspectFill" class="top_banner_img"></image>
		<!-- 主要内容 -->
		<view class="main_content">
			<!-- 会议基本信息 -->
			<view class="conference_basic_info">
				<view class="conference_name">2019中国康养产业创新发展论坛</view>
				<view class="conference_browse">
					<view class="browse_srea">
						<image src="http://qnimage.xiteng.com/icon_pageview@2x.png" class="browse_icon"></image>
						<view class="browse_num">浏览 1897</view>
					</view>
					<view class="browse_srea">
						<image src="http://qnimage.xiteng.com/icon_like@2x.png" class="browse_icon"></image>
						<view class="browse_num">收藏 49</view>
					</view>
				</view>
				<view class="conference_tickets_price">
					<view class="rmb_symbol">¥</view>
					<view class="price_num">50</view>
				</view>
				<view class="conference_time">
					<image src="http://qnimage.xiteng.com/icon_time@2x.png" class="browse_icon"></image>
					<view class="conference_time_text">2019.09.10 周六 13:30-17:00</view>
				</view>
				<view class="conference_time">
					<image src="http://qnimage.xiteng.com/dingwei@2x.png" class="browse_icon"></image>
					<view class="conference_time_text">北京西城宣武门外大街甲1环球财讯中心</view>
					<image src="http://qnimage.xiteng.com/image_location@2x.png" class="right_icon"></image>
				</view>
			</view>
			<!-- 中国老年和老年医学学会康养分会 -->
			<view class="go_affiliate">
				<image src="http://img2.imgtn.bdimg.com/it/u=2664341930,2707281610&fm=26&gp=0.jpg" mode="aspectFill" class="user_img"></image>
				<view class="center_cont">
					<view class="affiliate_name">中国老年和老年医学学会康养分会</view>
					<view class="attend_meetings_info">
						<view class="meeting_num">300+会议</view>
						<view class="join_meeting_num">5000+参加</view>
					</view>
				</view>
				<image src="http://qnimage.xiteng.com/arrow_right@2x.png" class="go_next_icon"></image>
			</view>
			<!-- 活动详情 -->
			<view class="activity_details">
				<view class="top_title">活动详情</view>
				<view class="activity_progress">
					<view class="activity_progress_num">01</view>
					<view class="activity_progress_text">活动介绍</view>
				</view>
				<view class="activity_details_content">
					进入21世纪以来，我国的经济高速发展，在短短的十几年的时间内就已经成为世界一流经济强国，但是在经济快速的同时，也伴随着些许的问题，人口老龄化就是其中较为突出的问题之一，
					根据预测据预测，到2050年中国老年人口将增至4.8亿，占全球老年人口的四分之一，为此国家频繁布局，提出了以“健康中国”为发展核心的战略部署，并出台了一系列鼓励有关康养产业的证政策，
					因此我国诞生了一大批以康养为宗旨的产业。
				</view>
				<view class="activity_details_img"></view>
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
.top_banner_img {
	width: 100%;
	height: 362upx;
}
.main_content {
	width: 100%;
}
.conference_basic_info {
	width: 100%;
	padding: 25upx 33upx 28upx 33upx;
	box-sizing: border-box;
	border-bottom: 20upx solid #f4f6f6;
}
.conference_name {
	color: #333333;
	font-size: 32upx;
	font-weight: 500;
}
.conference_browse {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 18upx;
}
.browse_icon {
	width: 36upx;
	height: 36upx;
	margin-right: 10upx;
}
.browse_num {
	color: #999999;
	font-size: 24upx;
}
.browse_srea {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-right: 30upx;
}
.conference_tickets_price {
	display: flex;
	flex-direction: row;
	align-items: center;
	color: #ff6f28;
	margin-top: 25upx;
	font-weight: 400;
	padding-bottom: 25upx;
	box-sizing: border-box;
	border-bottom: 1upx solid #e3e3e3;
	margin-bottom: 30upx;
}
.rmb_symbol {
	font-size: 26upx;
	margin-right: 10upx;
	margin-top: 5upx;
}
.price_num {
	font-size: 34upx;
}
.conference_time {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 13upx;
}
.conference_time_text {
	color: #333333;
	font-size: 28upx;
	flex: 1;
}
.right_icon {
	width: 52upx;
	height: 52upx;
}
.go_affiliate {
	width: 100%;
	padding: 29upx 30upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	align-items: center;
	border-bottom: 20upx solid #f4f6f6;
}
.user_img {
	width: 112upx;
	height: 112upx;
	border-radius: 10upx;
}
.center_cont {
	flex: 1;
	margin-left: 25upx;
}
.affiliate_name {
	color: #333333;
	font-size: 28upx;
}
.attend_meetings_info {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 20upx;
}
.go_next_icon {
	width: 30upx;
	height: 30upx;
}
.meeting_num,
.join_meeting_num {
	width: 140upx;
	color: #999;
	font-size: 24upx;
}
.meeting_num {
	border-right: 1upx solid #999999;
	margin-right: 30upx;
}
.activity_details {
	width: 100%;
	padding: 47rpx 33rpx;
	box-sizing: border-box;
}
.top_title {
	color: #333333;
	font-size: 32upx;
}
.activity_progress {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 50rpx;
}
.activity_progress_num {
	width: 52upx;
	height: 40upx;
	border-top: 5rpx solid #cdb675;
	border-right: 12rpx solid #cdb675;
	border-bottom: 5rpx solid #cdb675;
	border-left: 5rpx solid #cdb675;
	color: #cdb675;
	font-size: 28upx;
	text-align: center;
	font-weight: 500;
	line-height: 40upx;
}
.activity_progress_text {
	flex: 1;
	height: 45upx;
	margin-left: 20upx;
	color: #cdb675;
	font-size: 28upx;
	font-weight: 500;
	line-height: 45upx;
	border-bottom: 2rpx solid #cdb675;
}
.activity_details_content {
	color: #333333;
	font-size: 30upx;
	margin-top: 25upx;
	line-height: 50upx;
}
</style>
