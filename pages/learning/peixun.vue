<template>
	<div class="main">
		<wuc-tab :tab-list="tabList2" :tabCur="TabCur2" @change="tabChange2"></wuc-tab>
		<view class="item-group">
			<image :src="banner" class="banner" mode="aspectFill"></image>
			<!-- 加入培训计划 -->
			<view class="jihua">
				<image class="jihua-logo" src="http://qnimage.xiteng.com/11111.jpg" mode="aspectFill"></image>
				<view class="jihua-title">加入产业培训提升计划</view>
				<view class="jihua-desc">根据需求跟踪行业最新的培训课程</view>
				<view class="jihua-join">立即加入</view>
			</view>
			<!-- 专家团队 -->
			<view class="nav-title-wrapper"><naviTitle title="专家团队"></naviTitle></view>
			<view class="zhuanjia">
				<view class="zhuanjia-item">
					<image :src="avatar" class="avatar" mode="aspectFill"></image>
					<view class="zhuanjia-title">康养学会</view>
					<view class="zhuanjia-desc">12765位关注者</view>
					<view class="zhuanjia-item-button">+关注</view>
				</view>
				<view class="zhuanjia-item">
					<image :src="avatar" class="avatar" mode="aspectFill"></image>
					<view class="zhuanjia-title">康养学会</view>
					<view class="zhuanjia-desc">12765位关注者</view>
					<view class="zhuanjia-item-button">+关注</view>
				</view>
				<view class="zhuanjia-item">
					<image :src="avatar" class="avatar" mode="aspectFill"></image>
					<view class="zhuanjia-title">康养学会</view>
					<view class="zhuanjia-desc">12765位关注者</view>
					<view class="zhuanjia-item-button">+关注</view>
				</view>
			</view>

			<!-- 列表 -->
			<view class="list">
				<view class="list-item" @click="goCourseDetails">
					<image :src="avatar" class="list-item-image" mode="aspectFill"><view class="list-item-tips">限时特惠</view></image>
					<view class="list-item-name">老人护理课程</view>
					<view class="list-item-desc">5.4万人观看</view>
				</view>
				<view class="list-item" @click="goCourseDetails">
					<image :src="avatar" class="list-item-image" mode="aspectFill"><view class="list-item-tips">限时特惠</view></image>
					<view class="list-item-name">老人护理课程</view>
					<view class="list-item-desc">5.4万人观看</view>
				</view>
				<view class="list-item" @click="goCourseDetails">
					<image :src="avatar" class="list-item-image" mode="aspectFill"><view class="list-item-tips">限时特惠</view></image>
					<view class="list-item-name">老人护理课程</view>
					<view class="list-item-desc">5.4万人观看</view>
				</view>
			</view>
		</view>
	</div>
</template>

<script>
import WucTab from '@/components/wuc-tab/wuc-tab.vue';
import naviTitle from '@/components/navi-title.vue';

const banner =
	'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559565555450&di=c49d1ae925c49a9dc5a3ca291cf9a64d&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01ce8b582439aea84a0e282ba855d9.jpg';

const avatar =
	'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559567437010&di=c08a60c34d402310b550d28ab3091179&imgtype=0&src=http%3A%2F%2Fi3.hexun.com%2F2017-04-21%2F188923807.jpg';
export default {
	data() {
		return {
			banner,
			avatar,
			tabList2: [
				{
					name: '关注'
				},
				{
					name: '推荐'
				},
				{
					name: '养老护理'
				},
				{
					name: '营养保健'
				},
				{
					name: '企业管理'
				},
				{
					name: '产业新闻'
				}
			],
			TabCur2: 0
		};
	},

	components: {
		WucTab,
		naviTitle
		// JiaoLiu,
		// PeiXun
	},

	computed: {},

	methods: {
		tabChange(index) {
			this.TabCur = index;
		},
		tabChange2(index) {
			this.TabCur2 = index;
		},
		swiperChange2(e) {
			let { current } = e.target;
			this.TabCur2 = current;
		},
		goCourseDetails() {
			uni.navigateTo({
				url:'/pages/learning/courseDetails'
			})
		}
	},

	onReady() {}
};
</script>

<style>
/* @import "~@/styles/icon.scss"; */
.main {
	width: 100%;
	/* height: 100%; */
}

.banner {
	width: 100%;
	height: 320upx;
}

.list {
	width: 100%;
	padding: 30upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: space-between;
}

.list-item {
	width: 336upx;
	margin-top: 40upx;
}

.list-item-image {
	width: 336upx;
	height: 280upx;
	border-radius: 10upx;
	position: relative;
}

.list-item-tips {
	width: 114upx;
	height: 39upx;
	background: rgba(235, 46, 46, 1);
	color: #ffffff;
	position: absolute;
	left: 14upx;
	top: 16upx;
}

.list-item-name {
	font-size: 32upx;
	font-family: PingFangSC-Medium;
	font-weight: 500;
	color: rgba(51, 51, 51, 1);
	margin-top: 29upx;
}

.list-item-desc {
	font-size: 26upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(153, 153, 153, 1);
}

.zhuanjia-title {
	font-size: 30upx;
	font-family: PingFangSC-Medium;
	font-weight: 500;
	color: rgba(51, 51, 51, 1);
	line-height: 44upx;
}

.zhuanjia-desc {
	font-size: 24upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(153, 153, 153, 1);
	line-height: 44upx;

	text-align: center;
	margin-top: 30upx;
}

.jihua {
	margin-top: 40upx;
	margin-bottom: 60upx;
	margin-left: 30upx;
	width: 692upx;
	height: 237upx;
	background: rgba(255, 255, 255, 1);
	box-shadow: 0upx -1upx 18upx 0upx rgba(34, 32, 182, 0.12);
	border-radius: 10upx;

	position: relative;
}

.jihua-logo {
	width: 120upx;
	height: 90upx;

	position: absolute;
	left: 20upx;
	top: 70upx;
}

.jihua-title {
	color: #333333;
	font-size: 32upx;
	position: absolute;
	left: 215upx;
	top: 50upx;
}

.jihua-desc {
	color: #999999;
	font-size: 26upx;
	position: absolute;
	left: 215upx;
	top: 90upx;
}

.jihua-join {
	color: #ffffff;
	font-size: 26upx;
	position: absolute;
	left: 219upx;
	bottom: 41upx;
	background: #476aff;
	border-radius: 6upx;

	width: 140upx;
	height: 50upx;
	line-height: 50upx;
	text-align: center;
}

.nav-title-wrapper {
	padding: 0 20upx 23upx 20upx;
}

.zhuanjia-item-button {
	width: 104upx;
	height: 44upx;
	background: rgba(71, 106, 255, 1);
	border-radius: 10upx;

	color: 26upx;
	color: #ffffff;
	text-align: center;
}

.zhuanjia {
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	padding-bottom: 20upx;
	box-sizing: border-box;
	padding-left: 10upx;
	padding-right: 10upx;
}

.zhuanjia-item {
	width: 218upx;
	height: 299upx;
	background: rgba(255, 255, 255, 1);
	box-shadow: 0upx -1upx 18upx 0upx rgba(34, 32, 182, 0.12);
	border-radius: 10upx;
	display: flex;
	flex-direction: column;
	align-items: center;
	margin-right: 16upx;
}

.avatar {
	width: 100upx;
	height: 100upx;
	border-radius: 50%;
	margin-top: 24upx;
}

div,
scroll-view,
swiper {
	box-sizing: border-box;
}

div {
	font-size: 28upx;
	background-color: #f1f1f1;
}

.swiper {
	height: 1134upx;
}

.cu-bar {
	display: flex;
	position: relative;
	align-items: center;
	min-height: 100upx;
	justify-content: space-between;
}

.cu-bar .action {
	display: flex;
	align-items: center;
	height: 100%;
	justify-content: center;
	max-width: 100%;
	background-color: #ffffff;
}

.cu-bar .action:first-child {
	margin-left: 30upx;
	font-size: 30upx;
}

.solid,
.solid-bottom {
	position: relative;
}

.solid::after,
.solid-bottom::after {
	content: ' ';
	width: 200%;
	height: 200%;
	position: absolute;
	top: 0;
	left: 0;
	border-radius: inherit;
	transform: scale(0.5);
	transform-origin: 0 0;
	pointer-events: none;
	box-sizing: border-box;
}

.solid::after {
	border: 1upx solid rgba(0, 0, 0, 0.1);
}

.solid-bottom::after {
	border-bottom: 1upx solid rgba(0, 0, 0, 0.1);
}

.text-orange {
	color: #f37b1d;
}

.text-black {
	color: #333333;
}

.bg-white {
	background-color: #ffffff;
}

.padding {
	padding: 30upx;
}

.margin {
	margin: 30upx;
}

.margin-top {
	margin-top: 30upx;
}

.text-center {
	text-align: center;
}

,
.item-group {
	width: 100%;
	/* padding: 20upx; */
	background-color: #ffffff;
}

.btn-group > button {
	margin-left: 0;
}

.item {
	font-size: 28upx;
	color: #8f8f94;
	height: 56upx;
}

.btn-group {
	height: 80upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
	/* background: #007AFF; */
}

.btn-row {
	height: 60upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 0;
	justify-content: space-between;
	width: 350upx;
}
</style>
