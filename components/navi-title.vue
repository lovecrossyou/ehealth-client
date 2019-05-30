<template>
	<view class="main">
		<view class="title">
			{{title}}
		</view>
		<view class="subtitle">
			更多
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		props: {
			title: String,
			subtitle: String
		}
	}
</script>

<style>
	.main {
		height: 60upx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}

	.title {
		font-size: 32upx;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: rgba(51, 51, 51, 1);
		line-height: 44upx;
	}

	.subtitle {
		font-size: 24upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(119, 119, 119, 1);
	}
</style>
