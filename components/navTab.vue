<template>
	<view class="tab">
		<view class="item" v-for="(data,index) in items" :key="index" :class="[selectIndex===index? 'text-black': '']" @tap="tabSelect(index,$event)">
			{{data}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				selectIndex: 0,
				items: ['简介', '文化', '业务', '人力', '合作']
			};
		},
		methods: {
			tabSelect(index,event) {
				if (this.selectIndex === index) return false;
				this.selectIndex = index;
				this.$emit('change', index);
			}
		}
	}
</script>

<style>
	.tab {
		width: 100%;
		height: 100upx;
		display: flex;
		flex-direction: row;
		justify-content:space-between ;
		align-items: center;
		background-color: #fff;
		padding: 0 35upx;
		box-sizing: border-box;
	}

	.item {
		flex: 1;
		height: 100%;
		color: #666;
		font-size: 30upx;
		line-height: 100upx;
		text-align: center;
	}

	.text-black {
		flex: 1;
		height: 100%;
		color: #5871FE;
		font-size: 30upx;
		line-height: 100upx;
		text-align: center;
		border-bottom: 4upx solid #5871FE;
	}
</style>
