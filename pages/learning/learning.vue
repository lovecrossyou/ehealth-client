<template>
	<div class="main">
		<YLTab @change="tabChange"></YLTab>
		<block v-if="TabCur===0">
			<view class="item-group">
				<JiaoLiu></JiaoLiu>
			</view>
		</block>
		<block v-if="TabCur===1">
			<view class="item-group">
				<PeiXun></PeiXun>
			</view>
		</block>
		<block v-if="TabCur===2">
			<view class="item-group">
				<ZiXun></ZiXun>
			</view>
		</block>
	</div>

</template>


<script>
	import WucTab from '@/components/wuc-tab/wuc-tab.vue';
	import YLTab from '@/components/yltab.vue';
	import JiaoLiu from "./jiaoliu.vue";
	import PeiXun from "./peixun.vue";
	import ZiXun from "./zixun.vue";
	export default {
		data() {
			return {
				tabList2: [{
					name: '行业交流'
				}, {
					name: '培训'
				}, {
					name: '项目咨询'
				}],
				TabCur: 0,
			};
		},

		components: {
			WucTab,
			JiaoLiu,
			PeiXun,
			YLTab,
			ZiXun
		},

		computed: {},

		methods: {
			tabChange(index) {
				this.TabCur = index;
			},
			swiperChange2(e) {
				let {
					current
				} = e.target;
				this.TabCur2 = current;
			}
		},

		onReady() {}
	};
</script>

<style>
	/* @import "~@/styles/icon.scss"; */
	.main {
		width: 100%;
		overflow: hidden;
		
	}

	div,
	scroll-view,
	swiper {
		box-sizing: border-box;
	}

	div {
		font-size: 28upx;
		/* background-color: #f1f1f1; */
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
		/* padding: 20upx; */
		background-color: #FFFFFF;
		/* height: 100%; */
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
