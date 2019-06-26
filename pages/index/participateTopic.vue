<template>
	<view class="wrapper">
		<textarea value="" placeholder="写点什么..." class="text_area_box" auto-focus="true"/>
		<image src="http://qnimage.xiteng.com/shangchuan@2x.png" class="add_icon" @click="uploadingImages"></image>
		<view class="topic_title_text">#北京西城区自行出台康养养老规范，能否作为典范进行实行？</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {
		uploadingImages() {
			uni.chooseImage({
				count: 3, //默认9
				sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
				sourceType: ['album'], //从相册选择
				success: function(res) {
					console.log(JSON.stringify(res.tempFilePaths));
				}
			});
		}
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
	padding: 40upx 31upx;
	box-sizing: border-box;
}
.text_area_box {
	width: 100%;
	padding: 5upx;
	box-sizing: border-box;
	font-size: 32upx;
}
.add_icon {
	width: 160upx;
	height: 160upx;
}
.topic_title_text {
	width: 100%;
	height: 44upx;
	color: #5871fe;
	font-size: 22upx;
	margin-top: 30upx;
	font-weight: 400;
	line-height: 44upx;
	background-color: #F4F6F6;
	padding: 0 15upx;
	box-sizing: border-box;
}
</style>
