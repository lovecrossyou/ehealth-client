<template>
	<view class="wrapper">
		<!-- 分享 -->
		<view class="share_area">
			<image src="" class="share_icon"></image>
			<image src="http://qnimage.xiteng.com/share@2x.png" class="share_icon"></image>
		</view>
		<!-- 头部背景 -->
		<view class="blue_bg">
			<!-- 个签 & 头像 -->
			<view class="center_cont">
				<view class="signature_text">生命的全部的意义在于无穷地探索尚未知道的东西。</view>
				<image src="http://img2.imgtn.bdimg.com/it/u=3475306759,3888235577&fm=26&gp=0.jpg" mode="aspectFill" class="header_img"></image>
			</view>
			<!-- 名片 -->
			<view class="business_card">
				<view class="top_cont">
					<view class="personal_name">扎克伯格</view>
					<view class="personal_position">产品经理</view>
				</view>
				<view class="company_name">华为科技有限公司</view>
				<view class="bottom_info">
					<image src="http://qnimage.xiteng.com/icon_location@2x.png" class="phone_icon"></image>
					<view class="bottom_text">北京市西城区</view>
				</view>
				<view class="bottom_info">
					<image src="http://qnimage.xiteng.com/icon_phone@2x.png" class="phone_icon"></image>
					<view class="bottom_text">187 4334 6687</view>
				</view>
			</view>
		</view>
		<view class="main_content_area">
			<!-- 工作经历 -->
			<view class="work_experience">
				<view class="title_text">工作经历</view>
				<view class="company_details">
					<image src="https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=2424829431,3650179751&fm=58&w=121&h=140&img.PNG" mode="aspectFill" class="company_logo"></image>
					<view class="left_info">
						<view class="position">产品经理助理</view>
						<view class="company_nam">小米科技有限公司</view>
						<view class="work_time">2016年1月-2018年10月</view>
					</view>
				</view>
			</view>
			<!-- 教育经历 -->
			<view class="work_experience">
				<view class="title_text">教育经历</view>
				<view class="company_details">
					<image src="https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=3649282038,3012601376&fm=58&bpow=566&bpoh=566" mode="aspectFill" class="company_logo"></image>
					<view class="left_info">
						<view class="position">中国传媒大学</view>
						<view class="company_nam">艺术设计专业·本科</view>
						<view class="work_time">2014年-2018年</view>
					</view>
				</view>
			</view>
			<!-- 动态 -->
			<view class="from_industry">
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
			<button class="accept_btn">+加好友</button>
		</view>
	</view>
</template>

<script>
import Operation from '@/components/Operation.vue';
export default {
	data() {
		return {};
	},
	methods: {},
	components: {
		Operation
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.blue_bg {
	width: 100%;
	height: 470upx;
	background: linear-gradient(180deg, #5871fe, #5871fe, #fff);
	padding: 31upx;
	box-sizing: border-box;
}
.share_area {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
	padding: 31upx;
	box-sizing: border-box;
	background-color: #5871fe;
}
.share_icon {
	width: 34upx;
	height: 32upx;
}
.center_cont {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	margin-top: 30upx;
}
.signature_text {
	width: 445upx;
	color: #ffffff;
	font-size: 28upx;
}
.header_img {
	width: 160upx;
	height: 160upx;
	border-radius: 50%;
}
.business_card {
	width: 690upx;
	height: 330upx;
	background: #fff;
	box-shadow: 0px 1px 20px 0px rgba(18, 53, 114, 0.14);
	border-radius: 10upx;
	margin-top: 50upx;
	padding: 50upx;
	box-sizing: border-box;
}
.top_cont {
	display: flex;
	flex-direction: row;
	align-items: flex-end;
}
.personal_name {
	color: #333333;
	font-size: 42upx;
}
.personal_position {
	color: #333333;
	font-size: 30upx;
	margin-left: 30upx;
}
.company_name {
	color: #333333;
	font-size: 30upx;
	margin-top: 50upx;
	margin-bottom: 25upx;
	font-weight: bold;
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
.main_content_area {
	width: 100%;
	padding: 50upx 31upx 50upx 31upx;
	box-sizing: border-box;
	margin-top: 90upx;
}
.work_experience {
	width: 100%;
}
.title_text {
	color: #333;
	font-size: 32upx;
	margin: 80upx 0 30upx 0;
	font-weight: 500;
}
.company_details {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin: 15upx 0;
}
.company_logo {
	width: 120upx;
	height: 120upx;
	border-radius: 5upx;
}
.left_info {
	flex: 1;
	height: 120upx;
	margin-left: 25upx;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}
.position {
	color: #333;
	font-size: 30upx;
}
.company_nam {
	color: #777;
	font-size: 26upx;
}
.work_time {
	color: #999;
	font-size: 24upx;
}
.from_industry {
	width: 100%;
	background-color: #fff;
	margin-bottom: 80upx;
	margin-top: 50upx;
}
.publisher_info {
	width: 100%;
	padding: 29upx 0;
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
}
.accept_btn {
	width: 690upx;
	height: 80upx;
	background: linear-gradient(-90deg, rgba(137, 176, 253, 1), rgba(88, 113, 254, 1));
	border-radius: 40upx;
	color: #ffffff;
	font-size: 36upx;
	text-align: center;
	line-height: 80upx;
	position: fixed;
	left: 31upx;
	bottom: 50upx;
}
</style>
