<template>
	<view class="wrapper">
		<!-- 头部背景 -->
		<view class="top_bg">
			<view class="topic_title">北京西城区自行出台康养养老规范，能否作为行业典范进行实行？</view>
			<view class="bottom_area">
				<view class="discussion_num">1.5万人讨论</view>
				<view class="attention_btn">+ 关注</view>
			</view>
		</view>
		<!-- 讨论文章 -->
		<view class="discussion_article">
			<block v-for="(item, index) in topicContentList" :key="index">
				<view class="article_content">
					<view class="publisher_info">
						<image :src="item.userHeaderImg" mode="aspectFill" class="publisher_header_img"></image>
						<view class="publisher_presentation">
							<view class="publisher_name">{{ item.username }}</view>
							<view class="publisher_corporation">{{ item.userCompany }}</view>
						</view>
						<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
					</view>
					<view class="topic_title_text">{{ item.topicTitle }}</view>
					<view class="publish_content_text">{{ item.publishContent }}</view>
					<!-- 点赞 & 转发 & 评论 -->
					<Operation transpondNum="51" commentNum="785" likeNum="88"></Operation>
				</view>
			</block>
		</view>
		<!-- 参与话题按钮 -->
		<view class="participate_area" @click="goParticipate"><image src="http://qnimage.xiteng.com/btn_write@2x%20%281%29.png" class="participate_icon"></image></view>
	</view>
</template>

<script>
import Operation from '@/components/Operation.vue';
export default {
	data() {
		return {
			topicContentList: [
				{
					username: '张嘉',
					userHeaderImg: 'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3045822895,2238886242&fm=11&gp=0.jpg',
					userCompany: '北京富腾投资集团有限公司',
					topicTitle: '#北京西城区自行出台康养养老规范，能否作为典范进行实行？',
					publishContent:
						' 营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造的营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造额'
				},
				{
					username: '江滨',
					userHeaderImg: 'http://img5.imgtn.bdimg.com/it/u=3361018673,2640473848&fm=26&gp=0.jpg',
					userCompany: '江南集团有限公司',
					topicTitle: '#北京西城区自行出台康养养老规范，能否作为典范进行实行？',
					publishContent: '营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。'
				},
				{
					username: '宏强',
					userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=2532900942,931844899&fm=26&gp=0.jpg',
					userCompany: '龙源起航技术有钱公司',
					topicTitle: '#北京西城区自行出台康养养老规范，能否作为典范进行实行？',
					publishContent: '营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。'
				},
				{
					username: '张嘉',
					userHeaderImg: 'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3045822895,2238886242&fm=11&gp=0.jpg',
					userCompany: '北京富腾投资集团有限公司',
					topicTitle: '#北京西城区自行出台康养养老规范，能否作为典范进行实行？',
					publishContent:
						' 营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造的营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造额'
				}
			]
		};
	},
	methods: {
		goParticipate() {
			uni.navigateTo({
				url:'/pages/index/topic/participateTopic'
			})
		}
	},
	components: {
		Operation
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.top_bg {
	width: 100%;
	height: 430upx;
	background: linear-gradient(131deg, rgba(57, 160, 255, 1), rgba(132, 233, 255, 1));
	padding: 36upx 36upx 0 36upx;
	box-sizing: border-box;
}
.topic_title {
	color: #fff;
	font-size: 32upx;
	font-weight: bold;
	line-height: 44upx;
	margin-top: 130upx;
}
.bottom_area {
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	margin-top: 30upx;
}
.discussion_num {
	color: #ffffff;
	font-size: 26upx;
}
.attention_btn {
	width: 111upx;
	height: 49upx;
	background: #5871fe;
	border-radius: 4upx;
	color: #fff;
	font-size: 26upx;
	text-align: center;
	line-height: 49upx;
}
.discussion_article {
	width: 100%;
	background-color: #fff;
	border-radius: 20upx 20upx 0 0;
	margin-top: -50upx;
	padding: 50upx 31upx 0 31upx;
	box-sizing: border-box;
}
.article_content {
	width: 100%;
	border-bottom: 2upx solid #f4f6f6;
	padding-top: 20upx;
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
	padding: 0 31upx;
	box-sizing: border-box;
}
.hidden_arrows {
	width: 30upx;
	height: 16upx;
	margin: 10upx 0 0 10upx;
}
.topic_title_text {
	width: 100%;
	/* height: 44upx; */
	color: #5871fe;
	font-size: 22upx;
	margin-top: 30upx;
	font-weight: 400;
	line-height: 44upx;
	background-color: #F4F6F6;
	padding: 0 15upx;
	box-sizing: border-box;
}
.publish_content_text {
	color: #333;
	font-size: 30upx;
	margin-top: 15upx;
	line-height: 44upx;
}
.participate_icon {
	width: 130upx;
	height: 130upx;
	position: fixed;
	right: 20upx;
	bottom: 110upx;
}
</style>
