<template>
	<view class="wrapper">
		<!-- 头部背景图 -->
		<view class="top_bg_img">
			<image src="http://qnimage.xiteng.com/arrow_back@2x.png" class="back_icon" @click="backPage"></image>
			<image src="http://qnimage.xiteng.com/share@2x.png" class="share_icon"></image>
		</view>
		<!-- 公司基本信息 -->
		<view class="company_basic_info">
			<view class="top_info">
				<image
					src="https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1894992214,3473101703&fm=58&s=9095187A4F45B20B49AA4BB70300C02D&bpow=121&bpoh=75"
					mode="aspectFill"
					class="company_logo"
				></image>
				<view class="center_info">
					<view class="company_name">华为</view>
					<view class="attention_num">22035人关注</view>
				</view>
				<view class="attention_btn" v-if="isAttention" @click="giveAttention">+ 关 注</view>
				<view class="attention_btn" v-else @click="giveAttention">✓已关注</view>
			</view>
			<view class="explain_text">ICT（信息与通信）基础设施和智能终端提供商</view>
		</view>
		<!-- tab导航 -->
		<wuc-tab :tab-list="tabList2" :tabCur="TabCur2" @change="tabChange2" tab-class="text-center text-black bg-white" select-class="text-blue"></wuc-tab>
		<!-- 公司简介 -->
		<view class="company_profile">
			<view class="company_profile_title">公司简介</view>
			<view class="company_profile_cont">
				华为创立于1987年，是全球领先的ICT（信息与通信基础设施和智能终端提供商，我们致力于把数字世界带入每个人、每个家庭、每个组织，构建万物互联的智能世界。目前华为有18.8万员工，业务遍及170多个国家和地区，服务30多亿人口人口
			</view>
			<view class="bottom_border"></view>
		</view>
		<!-- 历程碑事件 -->
		<view class="milestone_incident">
			<view class="company_profile_title">历程碑事件</view>
			<uni-steps :data="[
				{title:'华为mate 10 Pro产品获得了来自全球各地的多家权威科技媒体的认可。',desc:'2019年1月11日'},
				{title:'华为以380.46亿美元的品牌价值提升至第25名，品牌价值增幅超过50%。',desc:'2019年2月9日'},
				{title:'12月27日，华为消费者业务CEO余承东正式宣布，华为2018年全球出货量（含荣耀）已经突破2亿台，并宣布为纪念这一新的历史记录',desc:'2019年12月17日'},
				{title:'2018年度华为手机（含荣耀）全球发货量突破2亿，稳居全球前三。',desc:'2018年12月1日'},]" 
				direction="column" 
				:active="-1"
				active-color="#5871FE">
			</uni-steps>
			<view class="bottom_border_line"></view>
		</view>
		<!-- 公司动态 -->
		<view class="company_dynamics">
			<view class="company_profile_title">公司动态</view>
			<view class="from_industry">
				<view class="publisher_info">
					<image src="https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1894992214,3473101703&fm=58&s=9095187A4F45B20B49AA4BB70300C02D&bpow=121&bpoh=75" mode="aspectFill" class="publisher_header_img"></image>
					<view class="publisher_presentation">
						<view class="publisher_name">华为</view>
						<!-- <view class="publisher_corporation">华为技术有限公司</view> -->
					</view>
					<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
				</view>
				<!-- 文字展开隐藏 -->
				<view class="publish_text">营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。</view>
				<view class="publish_image">
					<image src="http://img2.imgtn.bdimg.com/it/u=334514814,3940243718&fm=26&gp=0.jpg" mode="aspectFill"></image>
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=457503980,2486741247&fm=11&gp=0.jpg" mode="aspectFill"></image>
					<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4291489099,2387855543&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
				<!-- 点赞 & 转发 & 评论 -->
				<Operation transpondNum='555' commentNum='625' likeNum="85"></Operation>
			</view>
		</view>
	</view>
</template>

<script>
import WucTab from '@/components/wuc-tab/wuc-tab.vue';
import uniSteps from "@/components/uni-steps/uni-steps.vue";
import Operation from '@/components/Operation.vue';
export default {
	data() {
		return {
			isAttention: false,
			tabList2: [
				{
					name: '简介'
				},
				{
					name: '文化'
				},
				{
					name: '业务'
				},
				{
					name: '人力'
				},
				{
					name: '合作'
				}
			],
			TabCur2: 0
		};
	},
	methods: {
		giveAttention() {
			this.isAttention = !this.isAttention;
		},
		tabChange(index) {
			this.TabCur = index;
		},
		tabChange2(index) {
			this.TabCur2 = index;
		},
		backPage(){
			uni.navigateBack({
				
			})
		}
	},
	components: {
		WucTab,
		uniSteps,
		Operation
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
	background-color: #f3f3f3;
}
.top_bg_img {
	width: 100%;
	height: 395upx;
	background: url('http://qnimage.xiteng.com/background@2x.png') no-repeat center center;
	background-size: 100% 100%;
	padding: 42upx 33upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
}
.back_icon {
	width: 20upx;
	height: 34upx;
}
.share_icon {
	width: 34upx;
	height: 32upx;
}
.company_basic_info {
	width: 100%;
	height: 300upx;
	background-color: #fff;
	padding: 43upx 33upx;
	box-sizing: border-box;
	border-bottom: 1upx solid #e3e3e3;
	border-radius: 20upx 20upx 0 0;
	margin-top: -20upx;
	box-shadow: 0px 1px 18px 0px rgba(79, 125, 194, 0.4);
}
.top_info {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
}
.company_logo {
	width: 120upx;
	height: 120upx;
	background: rgba(255, 255, 255, 1);
	box-shadow: 0 1upx 18upx 0 rgba(79, 125, 194, 0.4);
	border-radius: 10upx;
}
.company_name {
	color: #282828;
	font-size: 36upx;
	font-weight: bold;
}
.attention_num {
	color: #999999;
	font-size: 26upx;
	margin-top: 15upx;
}
.center_info {
	flex: 1;
	margin-left: 31upx;
}
.attention_btn {
	width: 111upx;
	height: 49upx;
	background: #476aff;
	border-radius: 5upx;
	color: #ffffff;
	font-size: 22upx;
	text-align: center;
	line-height: 49upx;
}
.explain_text {
	color: #333333;
	font-size: 28upx;
	margin: 40upx 0 0 10upx;
}
.text-center {
	text-align: center;
}
.text-black {
	color: #666666;
	font-size: 30upx;
}
.text-black {
	color: #666666;
	font-size: 30upx;
}
.item-group {
	width: 100%;
	background-color: #ffffff;
}
.text-blue {
	color: #5871fe;
	font-size: 30upx;
}
.company_profile {
	width: 100%;
	margin-top: 20upx;
	padding: 50upx 33upx 0 33upx;
	box-sizing: border-box;
	background-color: #fff;
}
.company_profile_title {
	font-size: 28upx;
	color: #282828;
	font-weight: bold;
}
.company_profile_cont{
	color: #333;
	font-size: 30upx;
	margin-top: 25upx;
	line-height: 46upx;
}
.bottom_border{
	width: 100%;
	border-bottom: 1upx solid #e3e3e3;
	margin-top: 28upx;
}
.bottom_border_line{
	width: 100%;
	border-bottom: 1upx solid #e3e3e3;
}
.milestone_incident{
	width: 100%;
	padding: 45upx 33upx 0 33upx;
	box-sizing: border-box;
	background-color: #fff;
}
.company_dynamics{
	width: 100%;
	padding: 45upx 33upx 0 33upx;
	box-sizing: border-box;
	background-color: #fff;
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
	padding: 29upx 0;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
}
.publisher_header_img {
	width:74upx;
	height:74upx;
	box-shadow:0px 1upx 10upx 0px rgba(79,125,194,0.2);
	border-radius:4upx;
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
	margin-top: 15upx;
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
	/* padding: 0 31upx;
	box-sizing: border-box; */
}
.hidden_arrows {
	width: 30upx;
	height: 16upx;
	margin: 10upx 0 0 10upx;
}
.publish_image {
	width: 100%;
	/* padding: 0 31upx;
	box-sizing: border-box; */
	display: flex;
	flex-direction: row;
	/* justify-content: space-between; */
	margin-top: 27upx;
}
.publish_image image {
	width: 220upx;
	height: 220upx;
	border-radius: 6upx;
	margin: 0 8upx;
}
</style>
