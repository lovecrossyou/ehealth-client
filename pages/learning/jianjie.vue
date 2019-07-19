<template>
	<view class="jianjie_wrapper">
		<!-- 课程标题 -->
		<view class="course_title">康养建筑设计课程</view>
		<!-- 观看详情 -->
		<view class="watch_details">
			<image src="http://qnimage.xiteng.com/icon_look@2x.png" class="watch_icon"></image>
			<view class="watch_num">5.4万人已观看</view>
		</view>
		<!-- 课程详情图 -->
		<view class="course_details">
			<image src="http://qnimage.xiteng.com/image_two@2x.png" class="course_details_img" mode="widthFix"></image>
		</view>
		<!-- 购买 -->
		<view class="buy_course"><view class="buy_course_btn">购买 ¥199</view></view>
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
.jianjie_wrapper {
	width: 100%;
	padding: 40upx 31upx;
	box-sizing: border-box;
}
.course_title {
	color: #333333;
	font-size: 34upx;
	font-weight: 500;
	margin-left: 3upx;
}
.watch_details {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 20upx;
}
.watch_icon {
	width: 26upx;
	height: 18upx;
	margin-right: 8upx;
}
.watch_num {
	color: #999999;
	font-size: 24upx;
}
.course_details{
	width: 100%;
	padding: 40upx 0;
	box-sizing: border-box;
	margin-bottom: 130upx;
}
.course_details_img{
	width: 100%;
}
.buy_course {
	width: 100%;
	height: 128upx;
	box-shadow: 0px 1upx 10upx 0px rgba(0, 0, 0, 0.08);
	background: linear-gradient(0deg, #fff, #fff, rgba(255, 255, 255, 0.8));
	position: fixed;
	bottom: 0;
	left: 0;
	display: flex;
	flex-direction: row;
	align-items: center;
	padding: 0 30upx;
	box-sizing: border-box;
}
.buy_course_btn {
	width: 100%;
	height: 80upx;
	background: linear-gradient(-90deg, rgba(137, 176, 253, 1), rgba(88, 113, 254, 1));
	border-radius: 40upx;
	color: #ffffff;
	font-size: 36upx;
	text-align: center;
	line-height: 80upx;
	font-weight: 500;
}
</style>
