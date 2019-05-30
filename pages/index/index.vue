<template>
	<view class="container">
		<!-- 讨论列表 -->
		<view class="main">
			<swiper class="swiper-tall" :indicator-dots="indicatorDots" :autoplay="autoplay" :previous-margin="previousMargin"
			 :next-margin="nextMargin" :circular="circular" @change="change" :current="swiperCurrentIndex">
				<swiper-item class="swiper-container" v-for="(img,index) in imgs" :key="index" :item-id="img" :data-year="index">
					<view class="swiper-item">
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
			<view class="qiun-charts">
				<canvas canvas-id="canvasLineA" id="canvasLineA" class="charts" @touchstart="touchLineA"></canvas>
			</view>
		</view>

		<!-- 康养十大明星企业 -->
		<view class="star-companys">
			<naviTitle title="康养十大明星企业"></naviTitle>
			<scroll-view scroll-x="true" class="scroll-view_H" style="width: 100%" scroll-with-animation>
				<view class="companys">
					<starCompanyItem src="http://qnimage.xiteng.com/11@2x.png" title="泰康集团"></starCompanyItem>
					<starCompanyItem src="http://qnimage.xiteng.com/12@2x.png" title="康恩贝集团"></starCompanyItem>
					<starCompanyItem src="http://qnimage.xiteng.com/13@2x.png" title="天师集团"></starCompanyItem>
					<starCompanyItem src="http://qnimage.xiteng.com/14@2x.png" title="康养中心"></starCompanyItem>
				</view>
			</scroll-view>
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
					<image src="http://qnimage.xiteng.com/2.png" class="news-item-logo">

					</image>
					<view class="news-item-time">
						今天12:10
					</view>
				</view>

				<view class="news-item">
					<view class="news-item-title">
						乌丹星：分享了中国养老产业发展的 市场与战略思考。
					</view>
					<image src="http://qnimage.xiteng.com/3.png" class="news-item-logo">

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

			<scroll-view scroll-x="true" class="scroll-view_H" style="width: 100%" scroll-with-animation>
				<view class="report-items">
					<reportItem></reportItem>
					<reportItem></reportItem>
					<reportItem></reportItem>
				</view>

			</scroll-view>
		</view>
		<!-- 产业问答 -->
		<view class="ask-wrapper">
			<naviTitle title="产业问答"></naviTitle>
			<view class="ask-tabs">
				<view class="ask-tab-item-active">
					政策
				</view>
				<view class="ask-tab-item">
					企业管理
				</view>
				<view class="ask-tab-item">
					员工
				</view>
				<view class="ask-tab-item">
					行业
				</view>
			</view>

			<view class="ask-list">
				<view class="ask-list-item">
					<view class="ask-list-item-title">如何看待养老机构改革？</view>
					<view class="ask-list-item-footer">
						<image src="../../static/icon_man.png" class="ask-list-item-footer-icon"></image>
						<view class="participate-count">
							1562人已参与
						</view>
					</view>
				</view>
				<view class="ask-list-item">
					<view class="ask-list-item-title">北京的康养试运行是什么意思？</view>
					<view class="ask-list-item-footer">
						<image src="../../static/icon_man.png" class="ask-list-item-footer-icon"></image>
						<view class="participate-count">
							1.6万人已参与
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
	import naviTitle from "@/components/navi-title.vue";
	// import lineChart from '@/components/u-charts/pages/ucharts-demo/pie/pie.vue';
	
	import starCompanyItem from "./components/star-company-item.vue"
	import reportItem from "./components/report-item.vue"

	import Tabs from '@/components/tabs/tabs.vue'
	import TabPane from '@/components/tabs/tabPane.vue'
	
	import uCharts from '@/components/u-charts/u-charts.js';
	var _self;
	var canvaLineA=null;
	
	/*下面是服务器返回的数据格式*/
	var Data={
			"LineA": {
			  "categories": ["2012", "2013", "2014", "2015", "2016", "2017"],
			  "series": [{
				"name": "成交量A",
				"data": [35, 8, 25, 37, 4, 20]
			  }, {
				"name": "成交量B",
				"data": [70, 40, 65, 100, 44, 68]
			  }, {
				"name": "成交量C",
				"data": [100, 80, 95, 150, 112, 132]
			  }]
			}
		}
	
	export default {
		components: {
			naviTitle,
			// lineChart,
			starCompanyItem,
			reportItem
		},
		data() {
			return {
				cWidth:'',
				cHeight:'',
				pixelRatio:1,
				serverData:'',
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
			_self = this;
			this.cWidth=uni.upx2px(750);
			this.cHeight=uni.upx2px(500);
			this.getServerData();
		},
		methods: {
			getServerData(){
				_self.serverData=Data;
				let LineA={categories:[],series:[]};
				//这里我后台返回的是数组，所以用等于，如果您后台返回的是单条数据，需要push进去
				LineA.categories=Data.LineA.categories;
				LineA.series=Data.LineA.series;
				_self.showLineA("canvasLineA",LineA);
			},
			showLineA(canvasId,chartData){
				canvaLineA=new uCharts({
					$this:_self,
					canvasId: canvasId,
					type: 'line',
					fontSize:11,
					legend:false,
					dataLabel:false,
					dataPointShape:true,
					background:'#FFFFFF',
					pixelRatio:_self.pixelRatio,
					categories: chartData.categories,
					series: chartData.series,
					animation: true,
					xAxis: {
						type:'grid',
						gridColor:'#CCCCCC',
						gridType:'dash',
						dashLength:8
					},
					yAxis: {
						gridType:'dash',
						gridColor:'#CCCCCC',
						dashLength:8,
						splitNumber:5,
						min:10,
						max:180,
						format:(val)=>{return val.toFixed(0)+'元'}
					},
					width: _self.cWidth*_self.pixelRatio,
					height: _self.cHeight*_self.pixelRatio,
					extra: {
						lineStyle: 'straight'
					}
				});
				
			},
			change(e) {
				this.swiperCurrentIndex = e.detail.current;
				this.title = e.detail.currentItemId;
				for (let key in this.animationData) {
					if (e.detail.currentItemId == key) {
						// this.animation.scale(this.zoomParam).step();
						// this.animationData[key] = this.animation.export();
					} else {
						// this.animation.scale(1.0).step();
						// this.animationData[key] = this.animation.export();
					}
				}
			}
		}
	}
</script>

<style>
	page {
		/* height: 100%; */
		background: #f1f1f1;
		width: 100%;
		overflow: hidden;
	}

	.ask-tabs {
		padding: 27upx 0;
		box-sizing: border-box;
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.ask-list-item {
		width: 690upx;
		height: 168upx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0upx 1upx 12upx 0upx rgba(0, 0, 0, 0.08);
		border-radius: 4upx;
		position: relative;
		margin-bottom: 20upx;
	}

	.ask-list-item-title {

		font-size: 32upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(51, 51, 51, 1);
		line-height: 44upx;
		position: absolute;
		left: 44upx;
		top: 44upx;
	}

	.ask-list-item-footer {
		display: flex;
		flex-direction: row;
		align-items: center;
		position: absolute;
		left: 44upx;
		bottom: 37upx;
		margin-top: 30upx;
	}

	.participate-count {
		font-size: 26upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		line-height: 44upx;
		margin-left: 14upx;
	}

	.ask-list-item-footer-icon {
		width: 30upx;
		height: 26upx;
	}



	.ask-tab-item-active {
		width: 121upx;
		height: 46upx;
		background: rgba(156, 207, 255, 1);
		opacity: 0.6;
		border-radius: 4upx;
		margin-right: 20upx;
		line-height: 46upx;

		font-size: 28upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(16, 115, 227, 1);
		text-align: center;



	}

	.ask-tab-item {
		width: 149upx;
		height: 46upx;
		background: rgba(236, 235, 235, 1);
		border: 1upx solid rgba(213, 213, 213, 1);
		opacity: 0.6;
		border-radius: 4upx;
		margin-right: 20upx;

		font-size: 28upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(102, 102, 102, 1);
		line-height: 44upx;
		text-align: center;
	}

	.industry-index {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
		/* height: 480upx; */
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
		overflow: hidden;
	}

	.ask-wrapper {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
	}

	.report-items-wrapper {
		background-color: #FFFFFF;
		margin-top: 20upx;
		padding: 20upx 27upx;
		box-sizing: border-box;
		/* height: 190upx; */
	}

	.scroll-view_H {
		width: 750upx;
		/* height: 240upx; */

		overflow: scroll;
	}

	.scroll-view-item_H {
		width: 680upx;
		height: 190upx;
	}

	.bc_green {
		background-color: #0EA391;
	}

	.bc_red {
		background-color: #DC7004;
	}

	.report-items {
		display: flex;
		flex-direction: row;
		/* height: 120upx; */
		/* width: 100%; */
	}

	.report-item {
		width: 282upx;
		height: 190upx;
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
		border-radius: 30upx;
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
		width: 100%;
		height: 500upx;
		background-color: #FFFFFF;
		overflow: hidden;
	}

	.charts {
		width: 100%;
		height: 500upx;
		background-color: #FFFFFF;
		overflow: hidden;
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
