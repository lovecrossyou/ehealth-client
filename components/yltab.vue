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
				items: [ '项目','交流', '培训']
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
		height: 140upx;
		display: flex;
		flex-direction: row;
		align-items: flex-end;
		background-color: #fff;
		margin-top: 70upx;
		/* padding-top: 70upx;
		box-sizing: border-box; */
	}

	.item {
		height: 130upx;
		color: #999999;
		font-size: 38upx;
		margin-left: 30upx;
		line-height: 130upx;
	}

	.text-black {
		height: 130upx;
		color: #333333;
		font-size: 60upx;
		line-height: 130upx;
	}
</style>
