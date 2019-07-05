<template>
	<view class="main">
		<view class="nav-title">企脉</view>

		<view class="list">
			<view class="friends" @click="goMyFriends">
				<image src="http://qnimage.xiteng.com/icon_friends@2x.png" class="friend-icon"></image>
				<view class="friend-title">65位好友</view>
			</view>
			<view class="qimai" @click="searchCompaniesPulse">
				<image src="http://qnimage.xiteng.com/icon_find@2x.png" class="friend-icon"></image>
				<view class="friend-title">探索企脉</view>
			</view>
		</view>

		<view class="panel">
			<!-- 好友申请 -->
			<scroll-view scroll-x="true" class="scroll-view_H" style="width: 100%" scroll-with-animation>
				<view class="report-items">
					<view class="shenqing-item" v-for="(item, index) in list" :key="index">
						<image :src="item" :class="[index === 0 ? 'shenqing-item-icon-active' : 'shenqing-item-icon']" mode="aspectFill"></image>
						<view class="shenqing-item-label" :class="[index === 0 ? 'shenqing-item-label-active' : '']">好友申请</view>
					</view>
				</view>
			</scroll-view>
			<!-- 名片 -->
			<view class="business_card">
				<view class="basic_info">
					<view class="friend_name">扎克伯格</view>
					<view class="friend_post">产品经理</view>
				</view>
				<view class="friend_company">华为科技有限公司</view>
				<view class="bottom_info">
					<image src="http://qnimage.xiteng.com/icon_location@2x.png" class="phone_icon"></image>
					<view class="bottom_text">北京市西城区</view>
				</view>
				<view class="bottom_info">
					<image src="http://qnimage.xiteng.com/icon_phone@2x.png" class="phone_icon"></image>
					<view class="bottom_text">187 4334 6687</view>
				</view>
			</view>
			<!-- 公司简介 -->
			<view class="company_profile">
				<view class="company_top_text">公司简介</view>
				<view class="company_desc">
					华为技术有限公司创立于1987年，是全球领先的ICT（信息与通信）基础设施和智能终端提供商，我们致力于把数字世界带入每个人、每个家庭、每个组织，构建万物
				</view>
				<!-- <hideText></hideText> -->
			</view>
			<!-- 动态 -->
			<view class="from_industry">
				<view class="top_title"></view>
				<view class="publisher_info">
					<image
						src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1194115311,3137518246&fm=11&gp=0.jpg"
						mode="aspectFill"
						class="publisher_header_img"
					></image>
					<view class="publisher_presentation">
						<view class="publisher_name">任正非</view>
						<view class="publisher_corporation">华为技术有限公司</view>
					</view>
					<image src="http://qnimage.xiteng.com/icon_arrow_up@2x.png" class="hidden_arrows"></image>
				</view>
				<!-- 文字展开隐藏 -->
				<view class="publish_text">营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。</view>
				<view class="publish_image">
					<image src="http://img2.imgtn.bdimg.com/it/u=334514814,3940243718&fm=26&gp=0.jpg" mode="aspectFill"></image>
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=457503980,2486741247&fm=11&gp=0.jpg" mode="aspectFill"></image>
					<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4291489099,2387855543&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
				<!-- 点赞 & 转发 & 评论 -->
				<Operation transpondNum="555" commentNum="625" likeNum="85"></Operation>
			</view>
			<!-- 接受邀请按钮 -->
			<button class="accept_btn">接受申请</button>
		</view>
	</view>
</template>

<script>
import reportItem from '../index/components/report-item.vue';
// import hideText from './components/hideText.vue';
import Operation from '@/components/Operation.vue';
export default {
	components: {
		reportItem,
		// hideText,
		Operation
	},
	data() {
		return {
			list: [
				'http://qnimage.xiteng.com/WechatIMG12.jpeg',
				'http://qnimage.xiteng.com/leijun.jpg',
				'http://qnimage.xiteng.com/WechatIMG11.jpeg',
				'http://img4.imgtn.bdimg.com/it/u=2417263260,2496364790&fm=26&gp=0.jpg',
				'http://qnimage.xiteng.com/WechatIMG10.jpeg']
		};
	},
	methods: {
		goMyFriends(){
			uni.navigateTo({
				url:'/pages/business/myFriends'
			})
		},
		searchCompaniesPulse(){
			uni.navigateTo({
				url:'/pages/business/searchCompaniesPulse'
			})
		}
	}
};
</script>

<style>
.main {
	padding-top: 30upx;
	box-sizing: border-box;
}
.scroll-view_H {
	width: 100%;
	overflow: scroll;
	overflow-x: hidden;
}
.panel {
	width: 100%;
	background: rgba(255, 255, 255, 1);
	box-shadow: 0upx 1upx 18upx 0upx rgba(0, 0, 0, 0.14);
	border-radius: 40upx;
	margin-top: 20upx;
	padding: 46upx 0;
	box-sizing: border-box;
}
.report-items {
	display: flex;
	flex-direction: row;
	align-items: center;
}
.shenqing-item {
	position: relative;
	margin-right: 10upx;
}
.shenqing-item-icon-active {
	width: 176upx;
	height: 177upx;
	border: 4upx solid rgba(71, 106, 255, 1);
	border-radius: 50%;
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	margin-left: 31upx;
}
.shenqing-item-icon {
	width: 104upx;
	height: 104upx;
	border-radius: 50%;
	/* background: #0ea391; */
	margin-right: 42upx;
}
.shenqing-item-label {
	width: 100upx;
	height: 35upx;
	text-align: center;
	line-height: 35upx;
	background: rgba(255, 129, 60, 1);
	border-radius: 18upx;
	position: absolute;
	bottom: -10upx;
	text-align: center;
	color: #ffffff;
	font-size: 20upx;
	left: 3upx;
}
.shenqing-item-label-active {
	width: 100upx;
	height: 35upx;
	background: rgba(255, 129, 60, 1);
	border-radius: 18upx;
	position: absolute;
	bottom: 0upx;
	text-align: center;
	color: #ffffff;
	font-size: 20upx;
	left: 74upx;
	text-align: center;
	line-height: 35upx;
}
.nav-title {
	font-size: 60upx;
	font-family: PingFangSC-Medium;
	font-weight: 500;
	color: rgba(51, 51, 51, 1);
	line-height: 83upx;
	padding: 0 31upx;
	box-sizing: border-box;
}
.list {
	display: flex;
	flex-direction: row;
	padding: 0 30upx;
	box-sizing: border-box;
	justify-content: space-between;
	margin: 48upx 0 40upx 0;
}
.friends {
	background: url("http://qnimage.xiteng.com/image_background@2x.png");
	background-size: 328upx 120upx;
	width: 328upx;
	height: 120upx;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
}
.friend-icon {
	width: 40upx;
	height: 40upx;
}
.friend-title {
	font-size: 34upx;
	font-family: PingFangSC-Medium;
	font-weight: 500;
	color: rgba(255, 255, 255, 1);
	line-height: 44upx;
	margin-left: 17upx;
}
.qimai {
	background: url("http://qnimage.xiteng.com/image_find_background@2x.png");
	background-size: 328upx 120upx;
	width: 328upx;
	height: 120upx;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
}
.business_card {
	width: 690upx;
	height: 330upx;
	background: #f8f7f7;
	border-radius: 10px;
	margin: 30upx auto 56upx auto;
	padding: 50upx 57upx 30upx 57upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: column;
}
.basic_info {
	display: flex;
	flex-direction: row;
}
.friend_name {
	color: #333333;
	font-size: 42upx;
	font-weight: bold;
}
.friend_post {
	color: #333333;
	font-size: 30upx;
	margin-left: 35upx;
	margin-top: 15upx;
}
.friend_company {
	color: #333333;
	font-size: 30upx;
	font-weight: bold;
	margin: 50upx 0 27upx 0;
}
.bottom_info {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-bottom: 10upx;
	margin-left: -10upx;
}
.phone_icon {
	width: 40upx;
	height: 40upx;
}
.bottom_text {
	color: #333333;
	font-size: 30upx;
}
.company_profile {
	width: 100%;
	padding: 0 33upx;
	box-sizing: border-box;
}
.company_top_text {
	color: #333333;
	font-size: 32upx;
	font-weight: bold;
}

.company_desc{
	margin-top: 15upx;
	color: #333333;
	font-size: 30upx;
}
.from_industry {
	width: 100%;
	background-color: #fff;
	margin-bottom: 20upx;
}
.top_title {
	width: 100%;
	height: 65upx;
	color: #a6a6a8;
	font-size: 22upx;
	line-height: 65upx;
	border-bottom: 1upx solid #e3e3e3;
	padding: 0 31upx;
	box-sizing: border-box;
}
.publisher_info {
	width: 100%;
	padding: 29upx 31upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
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
.hidden_arrows {
	width: 30upx;
	height: 16upx;
	margin: 10upx 0 0 10upx;
}
.publish_image {
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	margin-top: 27upx;
}
.publish_image image {
	width: 220upx;
	height: 220upx;
	border-radius: 6upx;
	margin: 0 8upx;
}
.publish_text {
	width: 100%;
	color: #333;
	font-size: 30upx;
	padding: 0 31upx;
	box-sizing: border-box;
}
.accept_btn {
	width: 690upx;
	height: 80upx;
	background: linear-gradient(-90deg, rgba(88, 113, 254, 1), rgba(137, 176, 253, 1));
	border-radius: 40upx;
	color: #FFFFFF;
	font-size: 36upx;
	text-align: center;
	line-height: 80upx;
}
</style>
