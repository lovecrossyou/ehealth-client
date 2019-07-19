<template>
	<view class="wrapper">
		<!-- 课程视屏小窗口 -->
		<view class="video_window">
			<video
				id="myVideo"
				src="http://qnimage.xiteng.com/tih7PRDbSYUWsJHeY4gKskOW2T6z7jDV7G-t8w___16.mp4"
				@error="videoErrorCallback"
				controls
				page-gesture
				poster="http://qnimage.xiteng.com/image_one@2x.png"
			></video>
		</view>
		<!-- 简介 & 课程切换 -->
		<view class="">
			<navTab @change="tabChange"></navTab>
			<block v-if="TabCur === 0">
				<view class="item-group"><jianjie></jianjie></view>
			</block>
			<block v-if="TabCur === 1">
				<view class="item-group"><kecheng></kecheng></view>
			</block>
		</view>
	</view>
</template>

<script>
	import navTab from './components/navTab.vue';
	import jianjie from './jianjie.vue';
	import kecheng from './kecheng.vue';
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
		jianjie,
		kecheng
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.video_window > video {
	width: 100%;
	height: 500upx;
}
</style>
