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
		<!-- 回答详情 -->
		<view class="answer_details_wrapper">
			<view class="answer_tatal_num">355回答</view>
			<block v-for="(item, index) in answerQuestionList" :key="index">
				<view class="answer_question_details">
					<view class="publisher_info">
						<image :src="item.userImg" mode="aspectFill" class="publisher_header_img"></image>
						<view class="publisher_presentation">
							<view class="publisher_name">{{ item.userName }}</view>
							<view class="publisher_corporation">{{ item.company }}</view>
						</view>
						<view class="attention_btn" v-if="item.isAttention" @click="giveAttention(index)">+ 关注</view>
						<view class="attention_btn" v-else @click="giveAttention(index)">✓已关注</view>
					</view>
					<view class="publish_text">营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。</view>
					<view class="publish_image">
						<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=2780919478,3307421278&fm=26&gp=0.jpg" mode="aspectFill"></image>
						<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2103092801,962345008&fm=26&gp=0.jpg" mode="aspectFill"></image>
						<image src="http://img4.imgtn.bdimg.com/it/u=1509860559,1769982067&fm=26&gp=0.jpg" mode="aspectFill"></image>
					</view>
					<!-- 评论 & 点赞 -->
					<view class="comment_like_area">
						<view class="bottom_operation">
							<view class="operation_icon">
								<image src="http://qnimage.xiteng.com/btn_comment@2x.png" mode="aspectFill" style="width: 31upx;height: 28upx;"></image>
							</view>
							<view class="operation_num">{{ item.commentNum }}</view>
						</view>
						<view class="bottom_operation">
							<view class="operation_icon">
								<image src="http://qnimage.xiteng.com/btn_like%20@2x.png" mode="aspectFill" style="width: 30upx;height: 30upx;"></image>
							</view>
							<view class="operation_num">{{ item.likeNum }}</view>
						</view>
					</view>
				</view>
			</block>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			answerQuestionList: [
				{
					isAttention: false,
					userImg: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=390124251,2479429525&fm=26&gp=0.jpg',
					userName: '郭杰鹏',
					company: '珠江投资集团',
					publishText: '营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。',
					commentNum: '125',
					likeNum: '258'
				},
				{
					isAttention: false,
					userImg: 'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2273236243,559847510&fm=26&gp=0.jpg',
					userName: '家家乐',
					company: '江州集团',
					publishText: '营养领域康养行业怎么发展？2019第四届中国医疗生产制造。 ',
					commentNum: '45',
					likeNum: '859'
				}
			]
		};
	},
	methods: {
		giveAttention(index) {
			this.answerQuestionList[index].isAttention = !this.answerQuestionList[index].isAttention;
		}
	}
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
.answer_details_wrapper {
	width: 100%;
	padding: 43upx 31upx;
	box-sizing: border-box;
	background-color: #fff;
}
.answer_tatal_num {
	color: #282828;
	font-size: 34upx;
	font-weight: 500;
}
.answer_question_details {
	width: 100%;
	border-bottom: 1upx solid #e3e3e3;
	padding: 30upx 0;
	box-sizing: border-box;
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
	margin-top: 30upx;
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
.comment_like_area {
	display: flex;
	flex-direction: row;
	margin-top: 30upx;
	width: 40%;
	margin-left: 59%;
}
.bottom_operation {
	flex: 1;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: flex-end;
}
.operation_icon image {
	margin-right: 7upx;
}
.operation_num {
	color: #a6a6a8;
	font-size: 26upx;
	margin-top: 5upx;
}
</style>
