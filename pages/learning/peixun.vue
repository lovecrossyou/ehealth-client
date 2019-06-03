<template>
	<div class="main">
		<wuc-tab :tab-list="tabList2" :tabCur="TabCur2" @change="tabChange2" tab-class="text-center text-black bg-white"
		 select-class="text-blue text-xl"></wuc-tab>
		<swiper :current="TabCur2" class="swiper" duration="300" :circular="true" indicator-color="rgba(255,255,255,0)"
		 indicator-active-color="rgba(255,255,255,0)" @change="swiperChange2">
			<swiper-item v-for="(item,index) in tabList2" :key="index">
				<block v-if="index===0">
					<view class="item-group">
						<image :src="banner" class="banner" mode="aspectFill">

						</image>
						<view class="jihua">

						</view>
						<view class="nav-title-wrapper">
							<naviTitle title="专家团队"></naviTitle>
						</view>

						<view class="zhuanjia">
							<view class="zhuanjia-item">
								<image :src="avatar" class="avatar"></image>
								<view class="zhuanjia-title">
									康养学会
								</view>
								<view class="zhuanjia-desc">
									12765位关注者
								</view>
								<view class="zhuanjia-item-button">
									+关注
								</view>
							</view>
							<view class="zhuanjia-item">
								<image :src="avatar" class="avatar"></image>
								<view class="zhuanjia-title">
									康养学会
								</view>
								<view class="zhuanjia-desc">
									12765位关注者
								</view>
								<view class="zhuanjia-item-button">
									+关注
								</view>
							</view>
							<view class="zhuanjia-item">
								<image :src="avatar" class="avatar"></image>
								<view class="zhuanjia-title">
									康养学会
								</view>
								<view class="zhuanjia-desc">
									12765位关注者
								</view>
								<view class="zhuanjia-item-button">
									+关注
								</view>
							</view>
						</view>
					</view>
				</block>
				<block v-if="index===1">
					<view class="item-group">
						{{index}}
					</view>
				</block>
			</swiper-item>
		</swiper>
	</div>

</template>


<script>
	import WucTab from '@/components/wuc-tab/wuc-tab.vue';
	import naviTitle from "@/components/navi-title.vue";

	const banner =
		'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559565555450&di=c49d1ae925c49a9dc5a3ca291cf9a64d&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01ce8b582439aea84a0e282ba855d9.jpg'

	const avatar =
		'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559567437010&di=c08a60c34d402310b550d28ab3091179&imgtype=0&src=http%3A%2F%2Fi3.hexun.com%2F2017-04-21%2F188923807.jpg';
	export default {
		data() {
			return {
				banner,
				avatar,
				tabList2: [{
					name: '关注'
				}, {
					name: '推荐'
				}, {
					name: '养老护理'
				}, {
					name: '营养保健'
				}, {
					name: '企业管理'
				}, {
					name: '产业新闻'
				}],
				TabCur2: 0,
			};
		},

		components: {
			WucTab,
			naviTitle
			// JiaoLiu,
			// PeiXun
		},

		computed: {},

		methods: {
			tabChange(index) {
				this.TabCur = index;
			},
			tabChange2(index) {
				this.TabCur2 = index;
			},
			swiperChange2(e) {
				let {
					current
				} = e.target;
				this.TabCur2 = current;
			},
		},

		onReady() {}
	};
</script>

<style>
	/* @import "~@/styles/icon.scss"; */
	.main {
		width: 100%;
		height: 100%;
	}

	.banner {
		width: 100%;
		height: 320upx;
	}

	.zhuanjia-title {

		font-size: 30upx;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: rgba(51, 51, 51, 1);
		line-height: 44upx;
	}

	.zhuanjia-desc {

		font-size: 24upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		line-height: 44upx;
		
		text-align: center;
		margin-top: 30upx;
	}

	.jihua {
		margin-top: 40upx;
		margin-bottom: 60upx;
		margin-left: 30upx;
		width: 692upx;
		height: 237upx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0upx -1upx 18upx 0upx rgba(34, 32, 182, 0.12);
		border-radius: 10upx;
	}

	.nav-title-wrapper {
		padding: 0 20upx 23upx 20upx;

	}

	.zhuanjia-item-button {
		width: 104upx;
		height: 44upx;
		background: rgba(71, 106, 255, 1);
		border-radius: 10upx;
		
		
		color: 26upx;
		color: #FFFFFF;
		text-align: center;
	}

	.zhuanjia {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding-bottom: 20upx;
		box-sizing: border-box;
		padding-left: 10upx;
		padding-right: 10upx;
	}

	.zhuanjia-item {
		width: 218upx;
		height: 299upx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0upx -1upx 18upx 0upx rgba(34, 32, 182, 0.12);
		border-radius: 10upx;
		display: flex;
		flex-direction: column;
		align-items: center;
		/* margin-right: 16upx; */
	}

	.avatar {
		width: 100upx;
		height: 100upx;
		border-radius: 50%;
		margin-top: 24upx;
	}

	div,
	scroll-view,
	swiper {
		box-sizing: border-box;
	}

	div {
		font-size: 28upx;
		background-color: #f1f1f1;
	}

	.swiper {
		height: 1134upx;

	}

	.cu-bar {
		display: flex;
		position: relative;
		align-items: center;
		min-height: 100upx;
		justify-content: space-between;
	}

	.cu-bar .action {
		display: flex;
		align-items: center;
		height: 100%;
		justify-content: center;
		max-width: 100%;
		background-color: #ffffff;
	}

	.cu-bar .action:first-child {
		margin-left: 30upx;
		font-size: 30upx;
	}

	.solid,
	.solid-bottom {
		position: relative;
	}

	.solid::after,
	.solid-bottom::after {
		content: " ";
		width: 200%;
		height: 200%;
		position: absolute;
		top: 0;
		left: 0;
		border-radius: inherit;
		transform: scale(0.5);
		transform-origin: 0 0;
		pointer-events: none;
		box-sizing: border-box;
	}

	.solid::after {
		border: 1upx solid rgba(0, 0, 0, 0.1);
	}

	.solid-bottom::after {
		border-bottom: 1upx solid rgba(0, 0, 0, 0.1);
	}

	.text-orange {
		color: #f37b1d
	}

	.text-black {
		color: #333333;
	}

	.bg-white {
		background-color: #ffffff;
	}

	.padding {
		padding: 30upx;
	}

	.margin {
		margin: 30upx;
	}

	.margin-top {
		margin-top: 30upx;
	}

	.text-center {
		text-align: center;
	}

	,
	.item-group {
		width: 100%;
		/* padding: 20upx; */
		background-color: #FFFFFF;
	}

	.btn-group>button {
		margin-left: 0;
	}

	.item {
		font-size: 28upx;
		color: #8F8F94;
		height: 56upx;
	}

	.btn-group {
		height: 80upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		/* background: #007AFF; */
	}

	.btn-row {
		height: 60upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		margin-top: 0;
		justify-content: space-between;
		width: 350upx;
	}
</style>
