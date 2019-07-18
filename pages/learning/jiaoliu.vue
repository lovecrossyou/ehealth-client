<template>
	<view class="container">
		<view class="list">
			<view class="list-item" @click="goConferenceDetails">
				<view class="list-item-bg">
					<image src="http://qnimage.xiteng.com/tu.png" class="bg-image" mode="scaleToFill"></image>
					<view class="list-item-bg-tips">可报名</view>
					<image src="../../static/learn/icon_time.png" class="list-item-bg-clock"></image>
					<view class="time">2019-06-13 10：00</view>
					<view class="list-item-bg-button">立即报名</view>
				</view>
				<view class="title">2019第一届国际康养博览会</view>
				<view class="footer">
					<image src="../../static/learn/icon_location.png" class="icon_location"></image>
					<view class="addr">国家会议中心</view>
				</view>
			</view>

			<view class="list-item" @click="goConferenceDetails">
				<view class="list-item-bg">
					<image src="http://qnimage.xiteng.com/tu.png" class="bg-image" mode="scaleToFill"></image>
					<view class="list-item-bg-tips">可报名</view>
					<image src="../../static/learn/icon_time.png" class="list-item-bg-clock"></image>
					<view class="time">2019-06-13 10：00</view>
					<view class="list-item-bg-button">立即报名</view>
				</view>
				<view class="title">2019第一届国际康养博览会</view>
				<view class="footer">
					<image src="../../static/learn/icon_location.png" class="icon_location"></image>
					<view class="addr">国家会议中心</view>
				</view>
			</view>

			<view class="list-item" @click="goConferenceDetails">
				<view class="list-item-bg">
					<image src="http://qnimage.xiteng.com/tu.png" class="bg-image" mode="scaleToFill"></image>
					<view class="list-item-bg-tips">可报名</view>
					<image src="../../static/learn/icon_time.png" class="list-item-bg-clock"></image>
					<view class="time">2019-06-13 10：00</view>
					<view class="list-item-bg-button">立即报名</view>
				</view>
				<view class="title">2019第一届国际康养博览会</view>
				<view class="footer">
					<image src="../../static/learn/icon_location.png" class="icon_location"></image>
					<view class="addr">国家会议中心</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	methods: {
		goConferenceDetails() {
			uni.navigateTo({
				url: '/pages/learning/conferenceDetails'
			});
		}
	}
};
</script>

<style scoped>
.container {
	margin: auto;
}

.bg-image {
	position: absolute;
	left: 0;
	right: 0;
	width: 690upx;
	height: 360upx;

	padding-top: 30upx;
	box-sizing: border-box;
}

.list-item {
	padding: 0 30upx 34upx 30upx;
	box-sizing: border-box;
	background: #ffffff;
	border-bottom: solid 1upx #e1e1e1;

	margin-bottom: 30upx;
}

.list-item-bg {
	width: 100%;
	height: 360upx;
	position: relative;
	/* 
		display: flex;
		justify-content: center;
		align-items: center; */

	/* background-color: #2829DB; */
	border-radius: 10upx;
	background-color: #ffffff;
}

.list-item-bg-tips {
	position: absolute;
	left: 0upx;
	top: 40upx;
	width: 87upx;
	height: 42upx;
	background: rgba(255, 168, 0, 1);

	color: #ffffff;
	font-size: 24upx;
	text-align: center;
	border-radius: 10upx;
	line-height: 42upx;
}

.list-item-bg-button {
	position: absolute;
	right: 25upx;
	bottom: 22upx;
	width: 140upx;
	height: 50upx;
	background: rgba(255, 168, 0, 1);

	color: #ffffff;
	font-size: 24upx;
	text-align: center;
	border-radius: 10upx;
	line-height: 50upx;
}

.list-item-bg-title {
	width: 690px;
	height: 360px;
	opacity: 0.8;
	border-radius: 10px;
	margin-top: 28upx;
}

.list-item-bg-clock {
	position: absolute;
	left: 17upx;
	bottom: 23upx;
	width: 40upx;
	height: 40upx;
}

.time {
	position: absolute;
	left: 65upx;
	bottom: 23upx;
	font-size: 26upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(255, 255, 255, 1);
	/* background-color: #000000; */
	/* line-height:44upx; */
}

.title {
	font-size: 32upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(51, 51, 51, 1);
	line-height: 44upx;
	margin-top: 28upx;
	background-color: #ffffff;
}

.footer {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 22upx;
	background-color: #ffffff;
}

.icon_location {
	width: 40upx;
	height: 40upx;
}

.addr {
	font-size: 26upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(153, 153, 153, 1);
	line-height: 44upx;
	background-color: #ffffff;
}
</style>
