<template>
	<view class="wrapper">
		<!-- 新闻标题 -->
		<view class="news_title">2019北京养生养老健康旅游博览会新闻发布会在京召开</view>
		<view class="news_time">2015-06-25 11:20</view>
		<!-- 新闻内容 -->
		<view class="news_conent">
			“未富先老”一定程度上会造成劳动力人口比例下降、社会总体负担加重等问题，但如果解决得好不仅可以使老年人安度晚年，也可以拉动“银发经济”，
			进而促进经济社会繁荣稳定发展。目前不少地方开展了以居家养老为主、社区机构养老“三位一体”的养老模式,就是很好的探索与实践居家社区机构“三位一体”的养老模式，
			避免了发达国家在养老问题上所走过的弯路
		</view>
		<image src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2768465528,2575986303&fm=26&gp=0.jpg" mode="aspectFill" class="news_imgs"></image>
		<view class="news_conent">
			20世纪上半叶，发达国家通过社会保险法案,建立了大量的养老院,直到今天仍以养老院为主赡养老人。然而这些养老院看上去很美好，事实上存在着重大的缺陷：许多老人没有获得更有质量的生活；
			老人们与社会隔绝，少有尊严和掌控自己生活的权力；过分专注衡量健康的各项指标。
		</view>
		<view class="news_conent">到了20世纪80年代，新形式的养老院开始出现,叫做辅助生活重心。</view>
		<view class="news_conent">
            然而这些养老院看上去很美好，事实上存在着重大的缺陷：许多老人没有获得更有质量的生活；老人们与社会隔绝，少有尊严和掌控自己生活的权力。
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
	padding: 31upx;
	box-sizing: border-box;
}
.news_title {
	color: #282828;
	font-size: 40upx;
	line-height: 56upx;
	font-weight: bold;
}
.news_time {
	color: #999;
	font-size: 24upx;
	margin-top: 25upx;
}
.news_conent{
	color: #333;
	font-size: 30upx;
	line-height: 50upx;
	margin-top: 15upx;
}
.news_imgs{
	width: 100%;
	height: 400upx;
	margin-top: 18upx;
}
.total_discuss_list {
	display: flex;
	flex-direction: row;
	margin-top: 20upx;
	background-color: #fff;
	padding: 20upx 0;
	box-sizing: border-box;
}

.discuss_text {
	color: #333333;
	font-size: 32upx;
	font-weight: 500;
}

.discuss_num {
	color: #999999;
	font-size: 24upx;
	margin-top: 10upx;
}
.comment_list {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	background-color: #fff;
}
.comment_user_img {
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
.comment_content {
	margin-top: 30upx;
	color: #333333;
	font-size: 28upx;
}
</style>
