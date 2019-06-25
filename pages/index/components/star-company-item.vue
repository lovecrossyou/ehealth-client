<template>
	<view class="item-wrapper">
		<image :src="src" class="logo">

		</image>

		<view class="title">
			{{title}}
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			src: String,
			title: String
		}
	}
</script>

<style>
	.item-wrapper {
		width: 170upx;
		height: 245upx;

		display: flex;
		flex-direction: column;
		align-items: center;
		margin-right: 26upx;
	}

	.logo {
		width: 170upx;
		height: 170upx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0px -1px 18px 0px rgba(0, 0, 0, 0.08);
		border-radius: 50%;
	}

	.title {
		/* width: 109upx;
		height: 26upx; */
		font-size: 28upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(51, 51, 51, 1);
		line-height: 40upx;
		margin-top: 30upx;
	}
</style>
