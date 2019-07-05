<template>
	<view class="wrapper">
		<!-- 头部背景 -->
		<view class="blue_bg">
			<view class="share_area">
				<image src="" mode=""></image>
				<image src="" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	.wrapper{
		width: 100%;
	}
	.blue_bg{
		width: 100%;
		height:504upx;
		background:linear-gradient(180deg,#5871FE,#fff);
	}
	.share_area{
		display: flex;
		flex-direction: row;
		align-items: center;
		padding: 0 31upx;
		box-sizing: border-box;
	}
</style>
