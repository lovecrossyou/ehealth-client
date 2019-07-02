<template>
	<view class="wrapper">
		<!-- 报告简介 -->
		<view class="report_list" @click="goReporDetails(index)">
			<image src="http://qnimage.xiteng.com/6@2x.png" mode="aspectFill" class="report_cover"></image>
			<image src="http://qnimage.xiteng.com/report-vip@2x.png" class="free_report"></image>
			<view class="report_basic_details">
				<view class="report_name">2018年康养行业发展研究报告</view>
				<view class="report_vocation">行业：医疗</view>
				<view class="report_time">时间：2019-5-12</view>
				<view class="report_download">
					<image src="../../../static/icon_unload.png" class="download_icon"></image>
					<view class="download_num">2.34万</view>
				</view>
			</view>
		</view>
		<view class="main_content">
			<!-- 目录 -->
			<headline titleText="目录"></headline>
			<view class="directory_text">
				1、两会频现“养老”字眼，养老成为工作重点
				<br />
				2、银发经济亦是朝阳产业，5000 亿市场亟待满足
				<br />
				3、他山之石：介护保险制度催生日本养老 7000 亿大市场
				<br />
				4、国内养老模式：居家为主流，社区快速发展
				<br />
				5、投资建议
				<br />
				6、风险分析场
				<br />
				7、评级体系
				<br />
				8、医药生物
				<br />
				9、社区养老
				<br />
			</view>
			<!-- 内容 -->
			<headline titleText="内容"></headline>
			<view class="directory_text">
				<view class="bold_text">共96页<br/>升级为VIP可查看完整版内容</view>
			</view>
		</view>
		<!-- VIP查看完整版 -->
		<view class="download_area"><view class="download_btn">VIP查看完整版</view></view>
	</view>
</template>

<script>
import headline from '../components/headline.vue';
export default {
	data() {
		return {};
	},
	methods: {},
	components: {
		headline
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.report_list {
	width: 100%;
	padding: 30upx 31upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	align-items: center;
	position: relative;
	border-bottom: 20upx solid #f4f6f6;
}
.report_cover {
	width: 200upx;
	height: 200upx;
	/* opacity:0.7; */
	border-radius: 10upx;
}
.report_basic_details {
	margin-left: 30upx;
}
.report_name {
	color: #333333;
	font-size: 32upx;
	font-weight: 400;
}
.report_vocation {
	color: #999999;
	font-size: 24upx;
	margin-top: 15upx;
}
.report_time {
	color: #999999;
	font-size: 24upx;
	margin-top: 13upx;
}
.report_download {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 25upx;
}
.download_icon {
	width: 20upx;
	height: 20upx;
	margin-right: 10upx;
}
.download_num {
	color: #999999;
	font-size: 24upx;
}
.main_content {
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
	margin-bottom: 150upx;
}
.free_report {
	width: 82upx;
	height: 36upx;
	position: absolute;
	top: 29upx;
	left: 20;
}
.directory_text {
	color: #333;
	font-size: 30upx;
	line-height: 50upx;
}
.bold_text {
	color: #333;
	font-size: 30upx;
	font-weight: 500;
}
.download_area {
	width: 100%;
	height: 140upx;
	background-color: #fff;
	padding: 30upx;
	box-sizing: border-box;
	position: fixed;
	left: 0;
	bottom: 0;
}
.download_btn {
	width: 100%;
	height: 80upx;
	background:linear-gradient(-90deg,rgba(255,212,40,1),rgba(255,111,40,1));
	border-radius: 40upx;
	color: #ffffff;
	font-size: 36upx;
	text-align: center;
	line-height: 80upx;
	font-weight: 500;
}
</style>
