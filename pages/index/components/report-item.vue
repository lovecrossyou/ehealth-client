<template>
	<view class="item-wrapper">
		<image src="http://qnimage.xiteng.com/4@2x.png" class="logo" mode="aspectFill">

		</image>

		<view class="title">
			2019年康养行业发展研 究报告...
		</view>
		<view class="footer">
			<view class="time">
				2019-5-12
			</view>
			<view class="down-wrapper">
				<image  src="/static/icon_unload.png" class="download-icon">
				</image>
				<view class="count">
					2.34万
				</view>
			</view>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.item-wrapper {
		width: 282upx;
		height: 380upx;

		display: flex;
		flex-direction: column;
		align-items: center;
		margin-right: 23upx;
	}
	.download-icon{
		width: 20upx;
		height: 20upx;
		margin-right: 3upx;
	}

	.logo {
		width: 282upx;
		height: 212upx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0px -1px 18px 0px rgba(0, 0, 0, 0.08);
		border-radius: 12upx;
	}

	.title {
		font-size: 28upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(51, 51, 51, 1);
		line-height: 40upx;
		margin-top: 30upx;
	}

	.footer {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		width: 100%;
	}

	.time {
		font-size: 24upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		line-height: 44upx;
	}
	
	.down-wrapper{
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.count {
		font-size: 24upx;
		font-family: PingFangSC-Regular;
		font-weight: 400;
		color: rgba(153, 153, 153, 1);
		line-height: 44upx;
		margin-left: 3upx;
	}
</style>
