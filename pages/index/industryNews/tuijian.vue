<template>
	<view class="wrapper">
		<!-- 轮播 -->
		<view class="main" @click="goTopicDetails">
			<swiper
				class="swiper-tall"
				:indicator-dots="indicatorDots"
				:autoplay="autoplay"
				:previous-margin="previousMargin"
				:next-margin="nextMargin"
				:circular="circular"
				@change="change"
				:current="swiperCurrentIndex"
			>
				<swiper-item class="swiper-container" v-for="(img, index) in imgs" :key="index" :item-id="img" :data-year="index">
					<view class="swiper-item"><view class="basic_content">2019北京养生养老健康旅游博览会新闻发布会在京召开</view></view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 新闻列表-->
		<view class="industry-news">
			<block v-for="(item,index) in newsList" :key="index">
				<view class="news-item" @click="goNewsDetails">
					<view class="news-item-title">{{item.newsTitle}}</view>
					<image :src="item.newsImg" class="news-item-logo" mode="aspectFill"></image>
					<view class="news-item-time">{{item.newsTime}}</view>
				</view>
			</block>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			indicatorDots: false,
			autoplay: false,
			previousMargin: uni.upx2px(0) + 'px',
			nextMargin: uni.upx2px(45) + 'px',
			circular: true,
			zoomParam: 1.0,
			swiperCurrentIndex: 0,
			data: [],
			max: 0,
			imgs: ['1', '2', '3'],
			newsList:[
				{
					newsTitle:'乌丹星：分享了中国养老产业发展的市场与战略思考。',
					newsImg:'http://img4.imgtn.bdimg.com/it/u=431436975,2222605843&fm=11&gp=0.jpg',
					newsTime:'今天09:10'
				},
				{
					newsTitle:'刘德培：分享了中国养老产业发展方向。',
					newsImg:'http://img1.imgtn.bdimg.com/it/u=2073920882,1185123329&fm=26&gp=0.jpg',
					newsTime:'今天11:10'
				},{
					newsTitle:'陆华杰副会长分享了中国养老产业发展的市场与战略思考。',
					newsImg:'http://img0.imgtn.bdimg.com/it/u=379082643,3134404659&fm=26&gp=0.jpg',
					newsTime:'今天09:10'
				},{
					newsTitle:'乌丹星：分享了中国养老产业发展的市场与战略思考。',
					newsImg:'http://img4.imgtn.bdimg.com/it/u=431436975,2222605843&fm=11&gp=0.jpg',
					newsTime:'今天09:10'
				},
				{
					newsTitle:'刘德培：分享了中国养老产业发展方向。',
					newsImg:'http://img1.imgtn.bdimg.com/it/u=2073920882,1185123329&fm=26&gp=0.jpg',
					newsTime:'今天11:10'
				},{
					newsTitle:'陆华杰副会长分享了中国养老产业发展的市场与战略思考。',
					newsImg:'http://img0.imgtn.bdimg.com/it/u=379082643,3134404659&fm=26&gp=0.jpg',
					newsTime:'今天09:10'
				},
				
			]
		};
	},
	methods: {
		change(e) {
			this.swiperCurrentIndex = e.detail.current;
			this.title = e.detail.currentItemId;
			for (let key in this.animationData) {
				if (e.detail.currentItemId == key) {
					// this.animation.scale(this.zoomParam).step();
					// this.animationData[key] = this.animation.export();
				} else {
					// this.animation.scale(1.0).step();
					// this.animationData[key] = this.animation.export();
				}
			}
		},
		goNewsDetails(){
			uni.navigateTo({
				url:'/pages/index/industryNews/industryNewsDetails'
			})
		}
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
	padding: 35upx 31upx;
	box-sizing: border-box;
}
.main {
	width: 100%;
}
.swiper-tall {
	display: flex;
	align-items: center;
	height: 320upx;
	background-color: #ffffff;
}
.swiper-container {
	display: flex;
	align-items: center;
}
.swiper-item {
	display: flex;
	flex-wrap: wrap;
	justify-content: center;
	margin-left: 13upx;
	margin-right: 13upx;
	height: 320upx;
	width: 671upx;
	text-align: center;
	border-radius: 13upx;
	position: relative;
	background-size: 100%;
	background: url('http://img4.imgtn.bdimg.com/it/u=3438082709,2176902417&fm=11&gp=0.jpg') no-repeat center center;
	background-size: 100% 320upx;
}
.basic_content{
	color: #fff;
	font-size:30upx;
	font-weight:500;
	text-align: left;
	position:absolute ;
	left: 30upx;
	bottom: 30upx;
	line-height:40upx;
}
.industry-news {
	background-color: #ffffff;
	margin-top: 20upx;
}
.news-item {
	height: 200upx;
	position: relative;
	border-bottom: solid 1upx #f2f2f2;
}
.news-item-title {
	width: 477upx;
	font-size: 30upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(51, 51, 51, 1);
	position: absolute;
	top: 25upx;
	left: 0upx;
	line-height:42upx;
}
.news-item-logo {
	width: 179upx;
	height: 138upx;
	position: absolute;
	top: 25upx;
	right: 0upx;
}
.news-item-time {
	font-size: 24upx;
	font-family: PingFangSC-Regular;
	font-weight: 400;
	color: rgba(153, 153, 153, 1);
	line-height: 44upx;
	position: absolute;
	left: 0upx;
	bottom: 30upx;
}
</style>
