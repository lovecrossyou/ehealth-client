<template>
	<view class="wrapper">
		<!-- 头部 -->
		<view class="position_fixed">
			<view class="top_area">
				<view class="dynamic_title">动态</view>
				<view class="right_publish">
					<image src="http://qnimage.xiteng.com/btn_add@2x.png" class="publish_img"></image>
					<view>发布</view>
				</view>
			</view>
			<view class="search_wrapper">
				<view class="search_area">
					<image src="http://qnimage.xiteng.com/icon_search@2x.png" mode="" class="search_icon"></image>
					<input type="text" value="" placeholder="搜索行业动态" class="search_input" />
				</view>
			</view>
		</view>

		<!-- 来自你的产业朋友 -->
		<view class="from_industry margin_top">
			<view class="top_title">来自你的产业朋友</view>
			<view class="publisher_info"  @click="goCompanyDetails">
				<image src="http://img2.imgtn.bdimg.com/it/u=1961142815,2698003411&fm=26&gp=0.jpg" mode="aspectFill" class="publisher_header_img"></image>
				<view class="publisher_presentation">
					<view class="publisher_name">牛牧</view>
					<view class="publisher_corporation">北京富腾投资集团有限公司</view>
				</view>
				<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
			</view>
			<view class="publish_text" @click="goMomentDetails">
				营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。
			</view>
			<!-- 点赞 & 转发 & 评论 -->
			<Operation transpondNum="51" commentNum="785" likeNum="88"></Operation>
		</view>
		<!-- 来自你的投资人朋友 -->
		<view class="from_industry">
			<view class="top_title">来自你的投资人朋友</view>
			<view class="publisher_info" @click="goCompanyDetails">
				<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1194115311,3137518246&fm=11&gp=0.jpg" mode="aspectFill" class="publisher_header_img"></image>
				<view class="publisher_presentation">
					<view class="publisher_name">任正非</view>
					<view class="publisher_corporation">华为技术有限公司</view>
				</view>
				<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
			</view>
			<!-- 文字展开隐藏 -->
			<view class="publish_text"  @click="goMomentDetails">
				营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。
			</view>
			<view class="publish_image">
				<image src="http://img2.imgtn.bdimg.com/it/u=334514814,3940243718&fm=26&gp=0.jpg" mode="aspectFill"></image>
				<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=457503980,2486741247&fm=11&gp=0.jpg" mode="aspectFill"></image>
				<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4291489099,2387855543&fm=26&gp=0.jpg" mode="aspectFill"></image>
			</view>
			<!-- 点赞 & 转发 & 评论 -->
			<Operation transpondNum="555" commentNum="625" likeNum="85"></Operation>
		</view>
		<!-- 来自产业机构 -->
		<view class="from_industry">
			<view class="top_title">来自产业机构</view>
			<view class="organization_wrapper">
				<block v-for="(item, index) in organizationList" :key="index">
					<view class="organization_area">
						<image :src="item.img" class="organization_head_img" mode="aspectFill"></image>
						<view class="organization_name">{{ item.name }}</view>
						<view class="follower_num">{{ item.followerNum }}位关注者</view>
						<view class="attention_btn" v-if="item.isAttention" @click="giveAttention(index)">+ 关注</view>
						<view class="attention_btn" v-else @click="giveAttention(index)">✓已关注</view>
					</view>
				</block>
			</view>
		</view>
		<!-- 来自创新项目 -->
		<view class="from_industry">
			<view class="top_title">来自产业机构</view>
			<block block v-for="(item, index) in innovateList" :key="index">
				<view class="innovate_area">
					<image :src="item.img" mode="aspectFill" class="sleep_img"></image>
					<view class="right_project_detail">
						<view class="project_name">{{ item.name }}</view>
						<view class="financing_goal">融资目标：{{ item.financingGoal }}万</view>
						<view class="stock_num">出让股份：{{ item.stockNum }}%</view>
					</view>
				</view>
			</block>
		</view>
		<!-- 推广 -->
		<view class="from_industry">
			<view class="top_title">推广</view>
			<view class="publisher_info">
				<image
					src="https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1894992214,3473101703&fm=58&s=9095187A4F45B20B49AA4BB70300C02D&bpow=121&bpoh=75"
					mode="aspectFill"
					class="publisher_header_img"
					@click="goCompanyDetails"
				></image>
				<view class="publisher_presentation" @click="goCompanyDetails"><view class="publisher_name">华为</view></view>
				<view class="attention_btn">+ 关 注</view>
			</view>
			<view class="publish_text">
				凭借强大的研发实力和优秀的产品体验，过去一年华为手机已经完成了2亿部的出货目标，余承东此前曾表示，2019年华为手机的出货目标为2.5亿部，2020年要达到3亿部。而今年华为消费者业务也有望首次超越运营商、成为华为第一大核心业务。
			</view>
			<view class="publish_image">
				<image src="https://clubimg.club.vmall.com/data/attachment/forum/201902/05/222326kz1xbavj9lwusnwj.jpg" mode="aspectFill"></image>
				<image src="https://clubimg.club.vmall.com/data/attachment/forum/201902/05/222559nohzeyh1f3mvbtef.jpg" mode="aspectFill"></image>
				<image src="https://clubimg.club.vmall.com/data/attachment/forum/201902/05/222733fflvdln16j2iohd7.jpg" mode="aspectFill"></image>
			</view>
			<!-- 点赞 & 转发 & 评论 -->
			<Operation transpondNum="123" commentNum="22" likeNum="22"></Operation>
			<view class="publisher_info">
				<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3035998294,2703805772&fm=26&gp=0.jpg" mode="aspectFill" class="publisher_header_img"></image>
				<view class="publisher_presentation">
					<view class="publisher_name">雷军</view>
					<view class="publisher_corporation">小米科技有限公司</view>
				</view>
				<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
			</view>
			<view class="publish_text">
				营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。
			</view>
			<view class="publish_image">
				<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1205485994,167777535&fm=26&gp=0.jpg" mode="aspectFill"></image>
				<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2103092801,962345008&fm=26&gp=0.jpg" mode="aspectFill"></image>
			</view>
			<!-- 点赞 & 转发 & 评论 -->
			<Operation transpondNum="123" commentNum="22" likeNum="22"></Operation>
		</view>
	</view>
</template>
<script>
import hideText from './components/hideText.vue';
import Operation from '@/components/Operation.vue';
export default {
	data() {
		return {
			organizationList: [
				{
					isAttention: false,
					name: '康养学会',
					followerNum: '1258',
					img: 'http://img0.imgtn.bdimg.com/it/u=3186827157,3826494865&fm=11&gp=0.jpg'
				},
				{
					isAttention: true,
					name: '老年学学会',
					followerNum: '658',
					img: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=2083743049,1552929855&fm=15&gp=0.jpg'
				},
				{
					isAttention: false,
					name: '康养学会',
					followerNum: '529',
					img: 'http://img4.imgtn.bdimg.com/it/u=1593262122,2201972416&fm=26&gp=0.jpg'
				}
			],
			innovateList: [
				{
					name: '老年康养睡眠设备',
					img: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=2349968693,3858415515&fm=26&gp=0.jpg',
					financingGoal: '300',
					stockNum: '10'
				},
				{
					name: '中老年康养养生基地',
					img: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1589614470,1882171006&fm=26&gp=0.jpg',
					financingGoal: '450',
					stockNum: '13'
				}
			],
			isAttention: false
		};
	},
	components: {
		hideText,
		Operation
	},
	computed: {},
	methods: {
		giveAttention(index) {
			this.organizationList[index].isAttention = !this.organizationList[index].isAttention;
		},
		goCompanyDetails() {
			uni.navigateTo({
				url: '../companyDetails/companyDetails'
			});
		},
		goMomentDetails() {
			uni.navigateTo({
				url: '/pages/moment/momentDetails'
			});
		}
	}
};
</script>

<style>
.wrapper {
	width: 100%;
	background-color: #f4f6f6;
}
.top_area {
	width: 100%;
	height: 130upx;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	padding: 0 31upx;
	box-sizing: border-box;
	background-color: #fff;
}
.dynamic_title {
	font-size: 60upx;
	font-weight: bold;
}
.right_publish {
	display: flex;
	flex-direction: row;
	align-items: center;
}
.publish_img {
	width: 32upx;
	height: 32upx;
	margin-right: 8upx;
}
.search_wrapper {
	width: 100%;
	height: 150upx;
	display: flex;
	flex-direction: row;
	background: #fff;
	border-radius: 10upx;
	font-size: 28upx;
	padding: 15upx 30upx 0 30upx;
	box-sizing: border-box;
}
.search_area {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	background-color: #f5f4f4;
	height: 75upx;
	padding: 0 31upx;
	box-sizing: border-box;
}
.search_icon {
	width: 31upx;
	height: 31upx;
	margin-right: 13upx;
}
.search_input {
	flex: 1;
	height: 31upx;
	background-color: #f5f4f4;
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

	align-items: center;
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
.publish_text {
	width: 100%;
	color: #333;
	font-size: 30upx;
	padding: 0 31upx;
	box-sizing: border-box;
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
	/* justify-content: space-between; */
	margin-top: 27upx;
}
.publish_image image {
	width: 220upx;
	height: 220upx;
	border-radius: 6upx;
	margin: 0 8upx;
}
.organization_wrapper {
	width: 100%;
	background-color: #fff;
	padding: 28upx 31upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
}
.organization_area {
	width: 218upx;
	background-color: #f8f8f8;
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 24upx 0;
	box-sizing: border-box;
}
.organization_head_img {
	width: 100upx;
	height: 100upx;
	border-radius: 50%;
}
.organization_name {
	color: #333333;
	font-size: 30upx;
	font-weight: bold;
	margin-top: 18upx;
}
.follower_num {
	color: #999;
	font-size: 24upx;
	margin-top: 12upx;
}
.attention_btn {
	width: 104upx;
	height: 44upx;
	background: #476aff;
	border-radius: 10upx;
	color: #ffffff;
	font-size: 22upx;
	margin-top: 26upx;
	text-align: center;
	line-height: 44upx;
}
.innovate_area {
	width: 100%;
	padding: 30upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	background-color: #fff;
}
.sleep_img {
	width: 140upx;
	height: 140upx;
}
.right_project_detail {
	flex: 1;
	margin: 5upx 0 0 25upx;
	display: flex;
	flex-direction: column;
}
.project_name {
	color: #333333;
	font-size: 30upx;
	font-weight: bold;
}
.financing_goal {
	color: #777;
	font-size: 24upx;
	margin-top: 30upx;
}
.stock_num {
	color: #777;
	font-size: 24upx;
	margin-top: 5upx;
}
.position_fixed {
	width: 100%;
	/* position: fixed; */
	top: 0;
	left: 0;
	background-color: #fff;
	z-index: 99;
	/* margin-top: 50upx; */
}
.margin_top {
	/* margin-top: 280upx; */
}
</style>
