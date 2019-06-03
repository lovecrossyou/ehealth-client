<template>
	<view class="wrapper">
		<!-- 头部 -->
		<view class="top_area">
			<view class="dynamic_title">动态</view>
			<view class="right_publish">
				<image src="../../static/moment/btn_add@2x.png" class="publish_img"></image>
				<view>发布</view>
			</view>
		</view>
		<view class="search_area"><input type="text" value="" placeholder="搜索行业动态" /></view>
		<!-- 来自你的产业朋友 -->
		<view class="from_industry">
			<view class="top_title">来自你的产业朋友</view>
			<view class="publisher_info">
				<image src="http://img2.imgtn.bdimg.com/it/u=1961142815,2698003411&fm=26&gp=0.jpg" mode="aspectFill" class="publisher_header_img"></image>
				<view class="publisher_presentation">
					<view class="publisher_name">牛牧</view>
					<view class="publisher_corporation">北京富腾投资集团有限公司</view>
				</view>
				<image src="../../static/moment/icon_arrow_down@2x.png" class="hidden_arrows"></image>
			</view>
			<view class="publish_content">营养领域康养行业怎么发展？2019第四届中国医疗 器械高峰论坛，聚焦医疗产业原材料与生产制造。</view>
			<view class="publish_image">
				<image src="http://img2.imgtn.bdimg.com/it/u=334514814,3940243718&fm=26&gp=0.jpg" mode="aspectFill"></image>
				<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=457503980,2486741247&fm=11&gp=0.jpg" mode="aspectFill"></image>
				<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4291489099,2387855543&fm=26&gp=0.jpg" mode="aspectFill"></image>
			</view>
			<!-- 点赞 & 转发 & 评论 -->
			<view class="operation_list">
				<view class="bottom_operation">
					<view class="operation_icon">
						<image src="../../static/moment/btn_share@2x.png" mode="aspectFill"></image>
					</view>
					<view class="operation_num">1.5W</view>
				</view>
				<view class="bottom_operation">
					<view class="operation_icon">
						<image src="../../static/moment/btn_comment@2x.png" mode="aspectFill"></image>
					</view>
					<view class="operation_num">1.5W</view>
				</view>
				<view class="bottom_operation">
					<view class="operation_icon">
						<image src="../../static/moment/btn_like @2x.png" mode="aspectFill"></image>
					</view>
					<view class="operation_num">1.5W</view>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
export default {
	data() {
		return {};
	},
	components: {},
	computed: {},
	methods: {}
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
.search_area {
	width: 100%;
	height: 100upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	background: #fff;
	border-radius: 10upx;
	font-size: 28upx;
	padding: 0 30upx;
	box-sizing: border-box;
}
.search_area input {
	width: 690upx;
	height: 75upx;
	background: url('../../static/moment/icon_search@2x.png') no-repeat 4% center;
	background-size: 31upx 31upx;
	background-color: #f5f4f4;
	padding: 0 70upx;
	box-sizing: border-box;
}
.from_industry {
	width: 100%;
	background-color: #fff;
	padding-top: 70upx;
	box-sizing: border-box;
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
	margin-top: 8upx;
}
.hidden_arrows {
	width: 30upx;
	height: 16upx;
	margin: 10upx 0 0 10upx;
}
.publish_content{
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
	color: #333333;
	font-size: 30upx;
}
.publish_image{
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	margin-top: 27upx;
}
.publish_image image{
	width: 220upx;
	height: 220upx;
	border-radius: 6upx;
	margin: 0 8upx;
}
.operation_list{
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	padding: 36upx 68upx 25upx 68upx;
	box-sizing: border-box;
}
.bottom_operation{
	display: flex;
	flex-direction: row;
}
.operation_icon image{
	width: 40upx;
	height: 40upx;
	margin-right: 7upx;
}
.operation_num{
	color: #A6A6A8;
	font-size: 26upx;
	margin-top: 5upx;
}
</style>
