<template>
	<view class="wrapper">
		<!-- 搜索框 -->
		<view class="search_wrapper">
			<view class="search_area">
				<image src="http://qnimage.xiteng.com/icon_search@2x.png" mode="" class="search_icon"></image>
				<input type="text" value="" placeholder="搜索资讯" class="search_input" />
			</view>
		</view>
		<!-- tab导航 -->
		<view class="nav_tab_wrapper">
			<navTab @change="tabChange"></navTab>
			<block v-if="TabCur === 0">
				<view class="item-group">
					<tuijian></tuijian>
				</view>
			</block>
			<block v-if="TabCur === 1">
				<view class="item-group">222</view>
			</block>
			<block v-if="TabCur === 2"><view class="item-group">333</view></block>
		</view>
	</view>
</template>

<script>
	import navTab from '../components/navTab.vue';
	import tuijian from './tuijian.vue'
export default {
	data() {
		return {
			TabCur: 0
		};
	},
	methods: {
		tabChange(index) {
			this.TabCur = index;
		}
	},
	components:{
		navTab,
		tuijian
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.search_wrapper {
	width: 100%;
	display: flex;
	flex-direction: row;
	background: #fff;
	border-radius: 10upx;
	font-size: 28upx;
	padding: 15upx 30upx 0 30upx;
	box-sizing: border-box;
	margin-bottom: 38upx;
}
.search_area {
	width: 100%;
	display: flex;
	flex-direction: row;
	align-items: center;
	background-color: #f5f4f4;
	height: 60upx;
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
</style>
