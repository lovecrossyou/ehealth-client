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
				items: ['行业交流', '培训', '咨询']
			};
		},
		methods: {
			tabSelect(index,event) {
				if (this.selectIndex === index) return false;
				this.selectIndex = index;
				this.$emit('change', index);
				// console.log('xx', event);
			}
		}
	}
</script>

<style>
	.tab {
		height: 130upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		box-sizing: border-box;
		background: #FFFFFF;
	}

	.item {
		color: #999999;
		font-size: 38upx;
		margin-left: 30upx;

	}

	.text-black {
		color: #333333;
		font-size: 60upx;
	}
</style>
