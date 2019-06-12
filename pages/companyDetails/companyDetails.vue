<template>
	<view class="wrapper">
		<!-- 头部背景图 -->
		<view class="top_bg_img">
			<!-- <image src="http://qnimage.xiteng.com/arrow_back@2x.png" class="back_icon" @click="backPage"></image> -->
			<!-- <image src="http://qnimage.xiteng.com/share@2x.png" class="share_icon"></image> -->
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
		<view class="nav_tab_wrapper">
			<navTab @change="tabChange"></navTab>
			<block v-if="TabCur === 0">
				<view class="item-group">
					<jianjie></jianjie>
				</view>
			</block>
			<block v-if="TabCur === 1"><view class="item-group">22</view></block>
			<block v-if="TabCur === 2"><view class="item-group">333</view></block>
		</view>
	</view>
</template>

<script>
import navTab from '@/components/navTab.vue';
import jianjie from './jianjie.vue'
export default {
	data() {
		return {
			isAttention: false,
			TabCur: 0
		};
	},
	methods: {
		giveAttention() {
			this.isAttention = !this.isAttention;
		},
		backPage() {
			uni.navigateBack({});
		},
		tabChange(index) {
			this.TabCur = index;
		}
	},
	components: {
		navTab,
		jianjie
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
.nav_tab_wrapper {
	width: 100%;
	overflow: hidden;
	
}
.bg-white {
	background-color: #ffffff;
}
.item-group {
	width: 100%;
	background-color: #ffffff;
}

</style>
