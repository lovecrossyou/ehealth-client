<template>
	<view class="main">
		<view class="nav-title">
			企脉
		</view>

		<view class="list">
			<view class="friends">
				<image src="../../static/business/icon_friends.png" class="friend-icon"></image>
				<view class="friend-title">
					65位好友
				</view>
			</view>
			<view class="qimai">
				<image src="../../static/business/icon_find.png" class="friend-icon"></image>
				<view class="friend-title">
					探索企脉
				</view>
			</view>
		</view>


		<view class="panel">
			<!-- 好友申请 -->
			<scroll-view scroll-x="true" class="scroll-view_H" style="width: 100%" scroll-with-animation>
				<view class="report-items">
					<view class="shenqing-item" v-for="(item, index) in list" :key="index">
						<view :class="[index === 0? 'shenqing-item-icon-active': 'shenqing-item-icon']">

						</view>
						<view class="shenqing-item-label" :class="[index === 0? 'shenqing-item-label-active': '']">
							好友申请
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	import reportItem from "../index/components/report-item.vue"
	export default {
		components: {
			reportItem
		},
		data() {
			return {
				list: ['1', '2', '3', '4', '2', '3', '4', '2', '3', '4', '2', '3', '4']
			}
		},
		methods: {

		}
	}
</script>

<style>
	.main {
		/* padding: 30upx; */
	}

	.scroll-view_H {
		width: 750upx;
		overflow: scroll;
		overflow-x: hidden;
	}

	.panel {
		width: 750upx;
		background: rgba(255, 255, 255, 1);
		box-shadow: 0upx 1upx 18upx 0upx rgba(0, 0, 0, 0.14);
		border-radius: 40upx;
		margin-top: 20upx;

		height: 300upx;
	}

	.report-items {
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.shenqing-item {
		position: relative;
		margin-right: 10upx;
	}

	.shenqing-item-icon-active {
		width: 176upx;
		height: 177upx;
		border: 4upx solid rgba(71, 106, 255, 1);
		border-radius: 50%;
		position: relative;

		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.shenqing-item-icon {
		width: 104upx;
		height: 104upx;
		border-radius: 50%;
		background: #0EA391;
		margin-right: 42upx;
	}

	.shenqing-item-label {

		background: rgba(255, 129, 60, 1);
		border-radius: 18upx;

		position: absolute;
		bottom: -5upx;
		text-align: center;
		color: #FFFFFF;
		font-size: 22upx;
		left: 8upx;
	}

	.shenqing-item-label-active {

		background: rgba(255, 129, 60, 1);
		border-radius: 18upx;

		position: absolute;
		bottom: 0upx;
		text-align: center;

		color: #FFFFFF;
		font-size: 22upx;
		left: 38upx;
	}

	.nav-title {
		font-size: 60upx;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: rgba(51, 51, 51, 1);
		line-height: 83upx;
	}

	.list {
		display: flex;
		flex-direction: row;
		/* padding: 0 30upx; */
		box-sizing: border-box;
		justify-content: space-between;
		margin-top: 48upx;
	}

	.friends {
		background: url(../../static/business/image_background.png);
		background-size: 328upx 120upx;
		width: 328upx;
		height: 120upx;

		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}

	.friend-icon {
		width: 40upx;
		height: 40upx;
	}

	.friend-title {
		font-size: 34upx;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: rgba(255, 255, 255, 1);
		line-height: 44upx;
		margin-left: 17upx;
	}

	.qimai {
		background: url(../../static/business/image_find_background.png);
		background-size: 328upx 120upx;
		width: 328upx;
		height: 120upx;

		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
</style>
