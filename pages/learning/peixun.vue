<template>
	<div class="main">
		<wuc-tab :tab-list="tabList2" :tabCur="TabCur2" @change="tabChange2" tab-class="text-center text-black bg-white"
		 select-class="text-blue text-xl"></wuc-tab>
		<swiper :current="TabCur2" class="swiper" duration="300" :circular="true" indicator-color="rgba(255,255,255,0)"
		 indicator-active-color="rgba(255,255,255,0)" @change="swiperChange2">
			<swiper-item v-for="(item,index) in tabList2" :key="index">
				<block v-if="index===0">
					<view class="item-group">
						{{index}}
					</view>
				</block>
				<block v-if="index===1">
					<view class="item-group">
						{{index}}
					</view>
				</block>
			</swiper-item>
		</swiper>
	</div>

</template>


<script>
	import WucTab from '@/components/wuc-tab/wuc-tab.vue';

	export default {
		data() {
			return {
				tabList2: [{
					name: '关注'
				}, {
					name: '推荐'
				}, {
					name: '养老护理'
				}, {
					name: '营养保健'
				}, {
					name: '企业管理'
				}, {
					name: '产业新闻'
				}],
				TabCur2: 0,
			};
		},

		components: {
			WucTab,
			// JiaoLiu,
			// PeiXun
		},

		computed: {},

		methods: {
			tabChange(index) {
				this.TabCur = index;
			},
			tabChange2(index) {
				this.TabCur2 = index;
			},
			swiperChange2(e) {
				let {
					current
				} = e.target;
				this.TabCur2 = current;
			},
			swiperChange3(e) {
				let {
					current
				} = e.target;
				this.TabCur3 = current;
			},
			swiperChange4(e) {
				let {
					current
				} = e.target;
				this.TabCur4 = current;
			},
			swiperChange5(e) {
				this.TabCur5 = e.target.current;
			}
		},

		onReady() {}
	};
</script>

<style>
	/* @import "~@/styles/icon.scss"; */
	.main {
		width: 100%;
		height: 100%;
	}

	div,
	scroll-view,
	swiper {
		box-sizing: border-box;
	}

	div {
		font-size: 28upx;
		background-color: #f1f1f1;
	}

	.swiper {
		height: 1134upx;

	}

	.cu-bar {
		display: flex;
		position: relative;
		align-items: center;
		min-height: 100upx;
		justify-content: space-between;
	}

	.cu-bar .action {
		display: flex;
		align-items: center;
		height: 100%;
		justify-content: center;
		max-width: 100%;
		background-color: #ffffff;
	}

	.cu-bar .action:first-child {
		margin-left: 30upx;
		font-size: 30upx;
	}

	.solid,
	.solid-bottom {
		position: relative;
	}

	.solid::after,
	.solid-bottom::after {
		content: " ";
		width: 200%;
		height: 200%;
		position: absolute;
		top: 0;
		left: 0;
		border-radius: inherit;
		transform: scale(0.5);
		transform-origin: 0 0;
		pointer-events: none;
		box-sizing: border-box;
	}

	.solid::after {
		border: 1upx solid rgba(0, 0, 0, 0.1);
	}

	.solid-bottom::after {
		border-bottom: 1upx solid rgba(0, 0, 0, 0.1);
	}

	.text-orange {
		color: #f37b1d
	}

	.text-black {
		color: #333333;
	}

	.bg-white {
		background-color: #ffffff;
	}

	.padding {
		padding: 30upx;
	}

	.margin {
		margin: 30upx;
	}

	.margin-top {
		margin-top: 30upx;
	}

	.text-center {
		text-align: center;
	}

	,
	.item-group {
		width: 100%;
		padding: 20upx;
		background-color: #FFFFFF;
	}

	.btn-group>button {
		margin-left: 0;
	}

	.item {
		font-size: 28upx;
		color: #8F8F94;
		height: 56upx;
	}

	.btn-group {
		height: 80upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		/* background: #007AFF; */
	}

	.btn-row {
		height: 60upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		margin-top: 0;
		justify-content: space-between;
		width: 350upx;
	}
</style>
