<template>
	<view class="wrapper">
		<!-- 搜索框 -->
		<view class="search_wrapper">
			<view class="search_area">
				<image src="http://qnimage.xiteng.com/icon_search@2x.png" mode="" class="search_icon"></image>
				<input type="text" value="" placeholder="搜索资讯" class="search_input" />
			</view>
		</view>
		<!-- 筛选 -->
		<view class="content">
			<chooseLits :list="list" :arr="arr" @chooseLike="chooseLike"></chooseLits>
			<rich-text :nodes="ddd"></rich-text>
		</view>
	</view>
</template>

<script>
import chooseLits from '@/components/chooseLits/chooseLits.vue';
export default {
	data() {
		return {
			list: ['来源', '行业', '类型', '时间'],
			arr: [['综合排序', '价格降序', '价格升序'], ['类型不限', '高通过率', '利率低'], ['金额不限', '5k以下', '5k-10k', '10k以上']],
			i2: [0, 0, 0],
			ddd: '在飞云之下，啊哈哈哈哈，这风好大，我还是想她。'
		};
	},
	methods: {
		chooseLike(i1) {
			if (this.i2[i1[0]] != i1[1]) {
				this.i2[i1[0]] = i1[1];
			}
		}
	},
	components: { chooseLits }
};
</script>

<style scoped>
.wrapper {
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
}
.search_wrapper {
	width: 100%;
	display: flex;
	flex-direction: row;
	background: #fff;
	border-radius: 10upx;
	font-size: 28upx;
	padding: 15upx 30upx 0 30upx;
	box-sizing: border-box;
	margin-bottom: 38upx;
}
.search_area {
	width: 95%;
	display: flex;
	flex-direction: row;
	align-items: center;
	background-color: #f5f4f4;
	height: 60upx;
	padding: 0 31upx;
	box-sizing: border-box;
	border-radius: 10upx;
	margin: 0 auto;
}
.search_icon {
	width: 31upx;
	height: 31upx;
	margin-right: 13upx;
}
.search_input {
	flex: 1;
	height: 31upx;
	background-color: #f5f4f4;
}
.menu_wrapper {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
}
.content{
	
}
</style>
