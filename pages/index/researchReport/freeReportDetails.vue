<template>
	<view class="wrapper">
		<!-- 报告简介 -->
		<view class="report_list" @click="goReporDetails(index)">
			<image src="http://qnimage.xiteng.com/6@2x.png" mode="aspectFill" class="report_cover"></image>
			<image src="http://qnimage.xiteng.com/icon_free@2x.png" class="free_report"></image>
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
				<view class="bold_text">1、两会频现“养老”字眼，养老成为工作重点</view>
				<view>
					“养老”频现政府工作报告。今年两会期间，政府工作报告频现“养老”一词。通过梳理历年政府工作报告，我们发现今年变化是提及要降低企业缴费负担、
					大力发展社区养老以及推进多层次养老保障体系建设，归根到底是要降低负担、提高待遇以及大力发展性价比高的社区养老服务。
					<br />
					<br />
					两会期间多部委领导针对养老民生问题发言，直指养老服务供给不足和支付能力不足问题。发改委副主任连维良提出“一老一小”问题是最大的民生，
					表示党中央、国务院对城市养老一床难求问题高度重视，将通过“增能力、提质量、优结构”等一系列综合措施，加快解决养老领域总量不足、质量不
					优、发展不平衡的问题。财政部部长刘坤提出“养老金中央调剂制度”可解决部分省份收支压力较大的问题。一方面提高调剂比例，另一方面加大补助
					力度，按照中央与地方共同负担的原则，弥补收支缺口，加快规范养老保险省级统筹。
					<br />
					<br />
					商务部部长钟山提出，要促进实物消费提挡升级、服务消费提质
					扩容，当务之急是构建“养老、孝老、敬老”融为一体的政策体系与社会环境，着力补养老服务短板。从各部委领导的发言来看，国内养老突出的问题
					还是服务供给不足和支付能力不足，但把“一老一小”定义为最大的民生还是首次提出，说明在老龄化加速的大背景下，因养老产生的民生问题已经越
					来越突出，而国家对此重视程度也开始逐步提升。
				</view>
			</view>
		</view>
		<!-- 下载 -->
		<view class="download_area"><view class="download_btn">下载</view></view>
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
.free_report {
	width: 82upx;
	height: 36upx;
	position: absolute;
	top: 29upx;
	left: 20;
}
.main_content {
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
	margin-bottom: 150upx;
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
	background: linear-gradient(-90deg, rgba(137, 176, 253, 1), rgba(88, 113, 254, 1));
	border-radius: 40upx;
	color: #ffffff;
	font-size: 36upx;
	text-align: center;
	line-height: 80upx;
	font-weight: 500;
}
</style>
