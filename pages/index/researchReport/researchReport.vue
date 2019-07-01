<template>
	<view class="wrapper">
		<!-- 搜索框 -->
		<!-- <view class="search_wrapper">
			<view class="search_area">
				<image src="http://qnimage.xiteng.com/icon_search@2x.png" mode="" class="search_icon"></image>
				<input type="text" value="" placeholder="搜索资讯" class="search_input" />
			</view>
		</view> -->
		<!-- 筛选 -->
		<view class="content">
			<chooseLits :list="list" :arr="arr" @chooseLike="chooseLike"></chooseLits>
			<!-- <rich-text :nodes="ddd" class="main_content"></rich-text> -->
			<!-- 报告列表 -->
			<view class="report_list_wrapper">
				<block v-for="(item, index) in reportList" :key="index">
					<view class="report_list" @click="goReporDetails(index)">
						<image src="http://qnimage.xiteng.com/6@2x.png" mode="aspectFill" class="report_cover"></image>
						<image src="http://qnimage.xiteng.com/icon_free@2x.png" class="free_report" v-if="item.isFree"></image>
						<image src="http://qnimage.xiteng.com/report-vip@2x.png" class="free_report" v-else></image>
				
						<view class="report_basic_details">
							<view class="report_name">2018年康养行业发展研究报告</view>
							<view class="report_vocation">行业：医疗</view>
							<view class="report_time">时间：2019-5-12</view>
							<view class="report_download">
								<image src="../../../static/icon_unload.png" class="download_icon"></image>
								<view class="download_num">2.34万</view>
							</view>
						</view>
					</view>
				</block>
			</view>
		</view>
	</view>
</template>

<script>
import chooseLits from '@/components/chooseLits/chooseLits.vue';
export default {
	data() {
		return {
			list: ['来源', '行业', '类型', '时间'],
			arr: [['综合排序', '价格降序', '价格升序'], ['类型不限', '高通过率', '利率低'], ['金额不限', '5k以下', '5k-10k', '10k以上'], ['1月', '2月', '3月']],
			i2: [0, 0, 0],
			ddd: '在飞云之下，啊哈哈哈哈，这风好大，我还是想她。',
			reportList: [
				{
					isFree:true
				},{
					isFree:false
				},{
					isFree:true
				},{
					isFree:false
				}
			]
		};
	},
	methods: {
		chooseLike(i1) {
			if (this.i2[i1[0]] != i1[1]) {
				this.i2[i1[0]] = i1[1];
			}
		},
		goReporDetails(index){
			if(this.reportList[index].isFree == true){
				uni.navigateTo({
					url:'./freeReportDetails'
				})
			}else{
				uni.navigateTo({
					url:'./vipReportDetails'
				})
			}
			
		}
	},
	components: { chooseLits }
};
</script>

<style scoped>
.wrapper {
	width: 100%;
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
	background-color: pink;
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
.main_content {
	width: 100%;
	color: red;
	padding: 0 31upx;
	box-sizing: border-box;
	display: block;
	margin-top: 80upx;
}
.report_list_wrapper{
	padding-top: 80upx;
	background-color: #fff;
}
.report_list {
	width: 100%;
	padding: 25upx 31upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	align-items: center;
	position: relative;
}
.report_cover {
	width: 200upx;
	height: 200upx;
	/* opacity:0.7; */
	border-radius: 10upx;
}
.report_basic_details {
	margin-left: 30upx;
}
.report_name {
	color: #333333;
	font-size: 32upx;
	font-weight: 400;
}
.report_vocation {
	color: #999999;
	font-size: 24upx;
	margin-top: 15upx;
}
.report_time {
	color: #999999;
	font-size: 24upx;
	margin-top: 13upx;
}
.report_download {
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 25upx;
}
.download_icon {
	width: 20upx;
	height: 20upx;
	margin-right: 10upx;
}
.download_num {
	color: #999999;
	font-size: 24upx;
}
.free_report {
	width: 82upx;
	height: 36upx;
	position: absolute;
	top: 24upx;
	left: 20;
}
</style>
