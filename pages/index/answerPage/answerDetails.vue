<template>
	<view class="wrapper">
		<!-- 问题 -->
		<view class="question_area">
			<view class="question_title">如何看待养老机构改革？聚焦医疗产业原材料与生产制造？</view>
			<view class="participation_details">
				<image src="http://qnimage.xiteng.com/icon_man%20@2x.png" class="participation_icon"></image>
				<view class="participation_num">1562人已参与</view>
			</view>
			<view class="answer_question">
				<view class="answer_options right_border">
					<image src="http://qnimage.xiteng.com/btn_prive@2x.png" class="answer_icon"></image>
					<view class="answer_question_text">邀请回答</view>
				</view>
				<view class="answer_options">
					<image src="http://qnimage.xiteng.com/btn_write@2x.png" class="answer_icon"></image>
					<view class="answer_question_text">我来回答</view>
				</view>
			</view>
		</view>
		<!-- 回答原文 -->
		<view class="original_answer_area">
			<view class="publisher_info">
				<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=390124251,2479429525&fm=26&gp=0.jpg" mode="aspectFill" class="publisher_header_img"></image>
				<view class="publisher_presentation">
					<view class="publisher_name">郭杰鹏</view>
					<view class="publisher_corporation">珠江投资集团</view>
				</view>
				<view class="attention_btn">+ 关注</view>
			</view>
			<view class="publish_text">营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。</view>
			<image src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3378325347,2845401044&fm=11&gp=0.jpg" mode="aspectFill" class="publish_big_img"></image>
			<view class="publish_text">
				营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛。
			</view>
			<view class="publish_text">2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛。</view>
			<image src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3541708895,3025979664&fm=26&gp=0.jpg" mode="aspectFill" class="publish_big_img"></image>
			<view class="publish_text">聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？</view>
			<view class="publish_date">2019-05-23</view>
		</view>
		<!-- 评论总条数 -->
		<view class="total_discuss_list">
			<view class="discuss_text">评论</view>
			<view class="discuss_num">（99）</view>
		</view>
		<!-- 评论列表 -->
		<block v-for="(item, index) in commentList" :key="index">
			<view class="comment_list">
				<image :src="item.userHeaderImg" mode="aspectFill" class="comment_user_img"></image>
				<view class="right_area">
					<view class="comment_details">
						<view class="comment_user_details">
							<view class="comment_user_name">{{ item.username }}</view>
							<view class="comment_user_company">{{ item.userCompany }}</view>
						</view>
						<view class="comment_like_details">
							<image src="http://qnimage.xiteng.com/btn_like_n@2x.png" class="comment_like_icon"></image>
							<view class="comment_like_num">24</view>
						</view>
					</view>
					<view class="comment_content">{{ item.content }}</view>
				</view>
			</view>
		</block>
	</view>
</template>

<script>
export default {
	data() {
		return {
			commentList: [
				{
					username: '张嘉',
					userHeaderImg: 'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3457127321,2708165413&fm=26&gp=0.jpg',
					userCompany: '华为科技有限公司',
					content: '营养领域康养行业怎么发展？'
				},
				{
					username: '吴县',
					userHeaderImg: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=544141113,4203085230&fm=26&gp=0.jpg',
					userCompany: '小米科技有限公司',
					content: '大家参与起来！'
				},
				{
					username: '裔炯萨',
					userHeaderImg: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=266422256,4258569031&fm=26&gp=0.jpg',
					userCompany: '小米科技有限公司',
					content: '2019第四届中国医疗器械高峰论坛开展。'
				}
			]
		};
	},
	methods: {}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
	background-color: #f4f4f4;
}
.question_area {
	width: 100%;
	background-color: #fff;
	padding: 55upx 31upx 35upx 31upx;
	box-sizing: border-box;
	margin-bottom: 20upx;
}
.question_title {
	font-size: 32upx;
	color: #333333;
	font-weight: 400;
	line-height: 44upx;
}
.participation_details {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 30upx;
}
.participation_icon {
	width: 44upx;
	height: 44upx;
}
.participation_num {
	color: #999999;
	font-size: 26upx;
	margin-left: 7upx;
}
.answer_question {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	margin-top: 55upx;
}
.answer_options {
	flex: 1;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: center;
}
.answer_icon {
	width: 44upx;
	height: 44upx;
	margin-right: 7upx;
}
.answer_question_text {
	color: #5871fe;
	font-size: 28upx;
}
.right_border {
	border-right: 1upx solid #e3e3e3;
}
.original_answer_area {
	width: 100%;
	padding: 40upx 31upx;
	box-sizing: border-box;
	background-color: #fff;
	border-bottom: 1upx solid #e3e3e3;
}
.publisher_info {
	width: 100%;
	display: flex;
	flex-direction: row;
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
	margin-top: 20upx;
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
	/* justify-content: space-between; */
	margin-top: 27upx;
}
.publish_image image {
	width: 220upx;
	height: 220upx;
	border-radius: 6upx;
	margin: 0 8upx;
}
.attention_btn {
	width: 104upx;
	height: 44upx;
	background: #476aff;
	border-radius: 10upx;
	color: #ffffff;
	font-size: 22upx;
	text-align: center;
	line-height: 44upx;
}
.publish_big_img {
	width: 100%;
	height: 420upx;
	border-radius: 4upx;
	margin-top: 25upx;
}
.publish_date {
	color: #999999;
	font-size: 24upx;
	margin-top: 40upx;
}
comment_user_img {
	width: 60upx;
	height: 60upx;
	border-radius: 5upx;
}
.right_area {
	margin-left: 17upx;
	flex: 1;
	background-color: #fff;
	border-bottom: 1upx solid #e3e3e3;
	padding-bottom: 20upx;
	box-sizing: border-box;
}
.comment_details {
	display: flex;
	flex-direction: row;
	justify-content: space-between;
}
.comment_user_details {
	display: flex;
	flex-direction: column;
}
.comment_user_name {
	color: #333333;
	font-size: 28upx;
}
.comment_user_company {
	color: #999;
	font-size: 22upx;
}
.comment_like_details {
	display: flex;
	flex-direction: row;
	align-items: center;
}
.comment_like_icon {
	width: 32upx;
	height: 32upx;
	margin-right: 6upx;
}
.comment_like_num {
	color: #a6a6a8;
	font-size: 22upx;
	margin-top: 10upx;
}
.comment_like_blue_num {
	color: #5871fe;
	font-size: 22upx;
	margin-top: 10upx;
}
.comment_content {
	margin-top: 30upx;
	color: #333333;
	font-size: 28upx;
}
.comment_user_img {
	width: 60upx;
	height: 60upx;
	border-radius: 5upx;
}
.comment_list {
	width: 100%;
	/* height: 170upx; */
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	/* margin-top: 30upx; */
	background-color: #fff;
	padding: 31upx;
	box-sizing: border-box;
}
.total_discuss_list {
	display: flex;
	flex-direction: row;
	margin-top: 20upx;
	background-color: #fff;
	padding: 20upx 31upx;
	box-sizing: border-box;
}

.discuss_text {
	color: #333333;
	font-size: 32upx;
}

.discuss_num {
	color: #999999;
	font-size: 24upx;
	margin-top: 10upx;
}
</style>
