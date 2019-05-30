<template>
	<view class="container">
		<!-- 讨论列表 -->
		<view class="main">
			<swiper class="swiper-tall" :indicator-dots="indicatorDots" :autoplay="autoplay" :previous-margin="previousMargin"
			 :next-margin="nextMargin" :circular="circular" @change="change" :current="swiperCurrentIndex">
				<swiper-item class="swiper-container" v-for="(img,index) in imgs" :key="index" :item-id="img" :data-year="index">
					<view class="swiper-item" :animation="animationData[index]">
						<view class="xingfu">

						</view>
						<view class="yueka">
							1.5万人讨论
						</view>
						<view class="vip">
							北京西城区自行出台康养养老规范， 能否作为行业典范进行实行？
						</view>
					</view>
				</swiper-item>
			</swiper>
		</view>


		<!-- 行业指数发布 -->
		<view class="industry-index">
			<naviTitle title="行业指数发布"></naviTitle>
			<!-- <lineChart></lineChart> -->
		</view>

		<!-- 康养十大明星企业 -->
		<view class="star-companys">
			<naviTitle title="康养十大明星企业"></naviTitle>
			<view class="companys">
				<starCompanyItem></starCompanyItem>
				<starCompanyItem></starCompanyItem>
				<starCompanyItem></starCompanyItem>
				<starCompanyItem></starCompanyItem>
			</view>
		</view>

		<!-- 产业新闻 -->
		<view class="industry-news">
			<naviTitle title="产业新闻"></naviTitle>
			<view class="news">
				<view class="news-item">
					<view class="news-item-title">
						乌丹星：分享了中国养老产业发展的 市场与战略思考。
					</view>
					<image src="http://qnimage.xiteng.com/1.png" class="news-item-logo">

					</image>
					<view class="news-item-time">
						今天12:10
					</view>
				</view>

				<view class="news-item">
					<view class="news-item-title">
						乌丹星：分享了中国养老产业发展的 市场与战略思考。
					</view>
					<image src="http://qnimage.xiteng.com/1.png" class="news-item-logo">

					</image>
					<view class="news-item-time">
						今天12:10
					</view>
				</view>

				<view class="news-item">
					<view class="news-item-title">
						乌丹星：分享了中国养老产业发展的 市场与战略思考。
					</view>
					<image src="http://qnimage.xiteng.com/1.png" class="news-item-logo">

					</image>
					<view class="news-item-time">
						今天12:10
					</view>
				</view>

			</view>
		</view>
		<!-- 广告位 -->

		<!-- 研究报告 -->
		<view class="report-items-wrapper">
			<naviTitle title="研究报告"></naviTitle>
			<view class="report-items">
				<reportItem></reportItem>
				<reportItem></reportItem>
				<reportItem></reportItem>
			</view>
		</view>
		<!-- 产业问答 -->
		<view class="star-companys">
			<naviTitle title="产业问答"></naviTitle>
			
		</view>
	</view>
</template>
<script>
	import naviTitle from "@/components/navi-title.vue";
	import lineChart from './components/line-chart.vue';
	import starCompanyItem from "./components/star-company-item.vue"
	import reportItem from "./components/report-item.vue"

	import Tabs from '@/components/tabs/tabs.vue'
	import TabPane from '@/components/tabs/tabPane.vue'
	export default {
		components: {
			naviTitle,
			lineChart,
			starCompanyItem,
			reportItem
		},
		data() {
			return {
				screenHeight: 0,
				animationData: {
					0: {},
					1: {},
					2: {}
				},
				title: '0',
				indicatorDots: false,
				autoplay: false,
				previousMargin: uni.upx2px(82) + 'px',
				nextMargin: uni.upx2px(82) + 'px',
				circular: true,
				zoomParam: 1.0,
				swiperCurrentIndex: 0,
				data: [],
				max: 0,
				imgs: [
					'../../static/1.jpg',
					'../../static/2.jpg',
					'../../static/3.jpg'
				]
			}
		},
		computed: {

		},
		onLoad() {
			this.animation = uni.createAnimation();
			this.animation.scale(this.zoomParam).step();
			this.animationData[0] = this.animation.export();
		},
		methods: {
			change(e) {
				this.swiperCurrentIndex = e.detail.current;
				this.title = e.detail.currentItemId;
				for (let key in this.animationData) {
					if (e.detail.currentItemId == key) {
						this.animation.scale(this.zoomParam).step();
						this.animationData[key] = this.animation.export();
					} else {
						this.animation.scale(1.0).step();
						this.animationData[key] = this.animation.export();
					}
				}
			}
		}
	}
</script>

<style>
	page {
		height: 100%;
		background: #f1f1f1;
	}

	.industry-index {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
		height: 480upx;
	}

	.industry-news {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
	}

	.star-companys {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
		height: 380upx;
	}

	.report-items-wrapper {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
	}

	.report-items {
		display: flex;
		flex-direction: row;

	}

	.news {}

	.news-item {
		height: 164upx;
		position: relative;
		border-bottom: solid 1upx #F2F2F2;
	}

	.news-item-title {
		width: 477upx;
		font-size: 30upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(51, 51, 51, 1);
		position: absolute;
		top: 10upx;
		left: 0upx;
	}

	.news-item-logo {
		width: 179upx;
		height: 134upx;
		position: absolute;
		top: 10upx;
		right: 0upx;

	}

	.news-item-time {
		font-size: 24upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		line-height: 44upx;
		position: absolute;
		left: 0upx;
		bottom: 10upx;
	}


	.companys {
		display: flex;
		flex-direction: row;
		align-items: center;
		padding-top: 20upx;
		box-sizing: border-box;
	}

	.main {
		width: 100%;
	}

	.header {
		/* background: linear-gradient('radial',#FFBFC1,#FFFFFf); */
		width: 100%;
		height: 600upx;
		padding-top: 30upx;
		background-color: #FFFFFF;
	}

	.swiper-container {
		display: flex;
		align-items: center;

	}

	.swiper-item {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		margin-left: 20upx;
		margin-right: 20upx;
		height: 280upx;
		width: 671upx;
		text-align: center;
		broder-radius: 30upx;
		position: relative;
		/* background-color: #FF4161; */
		/* background: url('http://qnimage.xiteng.com/huiiyuan_ka@2x.png') no-repeat center center; */
		background-size: 100%;
		background: linear-gradient(left, #51B1F4, #9BF6F7);
	}

	/* uni-view {
		border-radius: 10upx;
	} */



	.swiper-tall {
		display: flex;
		align-items: center;
		height: 310upx;
		background-color: #FFFFFF;
	}



	.swiper-title {
		width: 750upx;
		text-align: center;
	}

	.xingfu {
		/* width: 153upx; */
		height: 50upx;
		width: 50upx;
		background-color: #F1F1F1;
		border-radius: 50%;
		position: absolute;
		top: 30upx;
		left: 40upx;
	}

	.yueka {
		/* width: 83upx; */
		/* height: 31upx; */
		font-size: 24upx;
		font-family: PingFang-SC-Medium;
		font-weight: bold;
		color: rgba(255, 255, 255, 1);
		/* line-height: 35upx; */
		position: absolute;
		left: 190upx;
		top: 40rpx;
	}

	.vip {
		font-size: 32upx;
		font-family: Ebrima;
		font-weight: bold;
		color: rgba(255, 245, 245, 1);
		/* line-height: 183upx; */
		position: absolute;
		top: 122upx;
		margin: auto;
	}

	.vip-items {
		width: 100%;
		/* padding-top: 60upx; */
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 60upx;
		box-sizing: border-box;
		/* background: #FFFFFF; */
	}

	.vip-item {
		/* margin-left: 80upx; */
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}

	.vip-item>image {
		width: 102upx;
		height: 102upx;
	}

	.title {
		padding-top: 10upx;
		font-size: 28upx;
		font-family: PingFang-SC-Medium;
		font-weight: 500;
		color: rgba(31, 31, 31, 1);
	}

	.desc {
		font-size: 24upx;
		font-family: PingFang-SC-Medium;
		font-weight: 500;
		color: rgba(153, 153, 153, 1);
		text-align: center;
	}

	.libao {
		margin-top: 20upx;
		background: #FFFFFF;
	}

	.libao-title {
		display: flex;
		flex-direction: row;
		height: 120upx;
		align-items: center;
		padding: 20upx;
		box-sizing: border-box;
	}

	.libao-items {
		display: flex;
		flex-direction: row;
		/* height: 308upx; */
		align-items: center;
		padding: 20upx;
		/* box-sizing: border-box; */

		margin-bottom: 160upx;
	}

	.libao-item {
		width: 218upx;
		height: 308upx;
		background: rgba(248, 248, 248, 1);
		border: 2upx solid rgba(255, 174, 185, 1);
		box-shadow: 0upx 5upx 35upx 0upx rgba(159, 21, 51, 0.13);
		border-radius: 8upx;
		margin-right: 15upx;
	}

	.libao-item>image {
		width: 218upx;
	}

	.libao-t {
		font-size: 32upx;
		font-family: PingFang-SC-Bold;
		font-weight: bold;
		color: rgba(31, 31, 31, 1);
		line-height: 80upx;
		text-align: center;
	}

	.libao-desc {
		font-size: 24upx;
		font-family: PingFang-SC-Regular;
		font-weight: bold;
		color: rgba(153, 153, 153, 1);
		line-height: 80upx;
	}

	.btn_vip {
		width: 669upx;
		height: 92upx;
		font-size: 32upx;
		font-family: PingFang-SC-Medium;
		font-weight: bold;
		background: #FF2C46;
		text-align: center;
		line-height: 92upx;
		border-radius: 46upx;
		color: #FFFFFF;
		position: fixed;
		bottom: 58upx;
		left: 40upx;
		right: 40upx;
	}

	.qiun-padding {
		padding: 2%;
		width: 96%;
	}

	.qiun-wrap {
		display: flex;
		flex-wrap: wrap;
	}

	.qiun-rows {
		display: flex;
		flex-direction: row !important;
	}

	.qiun-columns {
		display: flex;
		flex-direction: column !important;
	}

	.qiun-common-mt {
		margin-top: 10upx;
	}

	.qiun-bg-white {
		background: #FFFFFF;
	}

	.qiun-title-bar {
		width: 96%;
		padding: 10upx 2%;
		flex-wrap: nowrap;
	}

	.qiun-title-dot-light {
		border-left: 10upx solid #0ea391;
		padding-left: 10upx;
		font-size: 32upx;
		color: #000000
	}

	/* 通用样式 */
	.qiun-charts {
		width: 750upx;
		height: 500upx;
		background-color: #FFFFFF;
	}

	.charts {
		width: 750upx;
		height: 500upx;
		background-color: #FFFFFF;
	}

	/* 横屏样式 */
	.qiun-charts-rotate {
		width: 700upx;
		height: 1100upx;
		background-color: #FFFFFF;
		padding: 25upx;
	}

	.charts-rotate {
		width: 700upx;
		height: 1100upx;
		background-color: #FFFFFF;
	}

	/* 圆弧进度样式 */
	.qiun-charts3 {
		width: 750upx;
		height: 250upx;
		background-color: #FFFFFF;
		position: relative;
	}

	.charts3 {
		position: absolute;
		width: 250upx;
		height: 250upx;
		background-color: #FFFFFF;
	}

	.qiun-tip {
		display: block;
		width: auto;
		overflow: hidden;
		padding: 15upx;
		height: 30upx;
		line-height: 30upx;
		margin: 10upx;
		background: #ff9933;
		font-size: 30upx;
		border-radius: 8upx;
		justify-content: center;
		text-align: center;
		border: 1px solid #dc7004;
		color: #FFFFFF;
	}
</style>
