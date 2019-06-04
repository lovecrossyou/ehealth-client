<template>
	<view class="operation_list">
		<view class="bottom_operation">
			<view class="operation_icon"><image src="../../static/moment/btn_share@2x.png" mode="aspectFill"></image></view>
			<view class="operation_num">{{ transpondNum }}</view>
		</view>
		<view class="bottom_operation">
			<view class="operation_icon"><image src="../../static/moment/btn_comment@2x.png" mode="aspectFill"></image></view>
			<view class="operation_num">{{ commentNum }}</view>
		</view>
		<view class="bottom_operation">
			<view class="operation_icon"><image src="../../static/moment/btn_like@2x.png" mode="aspectFill"></image></view>
			<view class="operation_num">{{ likeNum }}</view>
		</view>
	</view>
</template>

<script>
import Vue from 'vue';
export default {
	data() {
		return {};
	},
	props: {
		transpondNum: String,
		commentNum: String,
		likeNum: String
	},
	methods: {}
};
</script>

<style scoped>
.operation_list {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	padding: 36upx 75upx 25upx 75upx;
	box-sizing: border-box;
	background-color: #fff;
}
.bottom_operation {
	display: flex;
	flex-direction: row;
}
.operation_icon image {
	width: 40upx;
	height: 40upx;
	margin-right: 7upx;
}
.operation_num {
	color: #a6a6a8;
	font-size: 26upx;
	margin-top: 5upx;
}
</style>
