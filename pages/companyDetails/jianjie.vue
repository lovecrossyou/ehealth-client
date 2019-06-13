<template>
	<view class="wrapper">
		<!-- 公司简介 -->
		<view class="company_profile">
			<view class="company_profile_title">公司简介</view>
			<view class="company_profile_cont">
				华为创立于1987年，是全球领先的ICT（信息与通信基础设施和智能终端提供商，我们致力于把数字世界带入每个人、每个家庭、每个组织，构建万物互联的智能世界。目前华为有18.8万员工，业务遍及170多个国家和地区，服务30多亿人口人口...
			</view>
			<view class="bottom_border"></view>
		</view>
		<!-- 历程碑事件 -->
		<view class="milestone_incident">
			<view class="company_profile_title">历程碑事件</view>
			<uni-steps :data="[
				{title:'华为mate 10 Pro产品获得了来自全球各地的多家权威科技媒体的认可。',desc:'2019年1月11日'},
				{title:'华为以380.46亿美元的品牌价值提升至第25名，品牌价值增幅超过50%。',desc:'2019年2月9日'},
				{title:'12月27日，华为消费者业务CEO余承东正式宣布，华为2018年全球出货量（含荣耀）已经突破2亿台，并宣布为纪念这一新的历史记录',desc:'2019年12月17日'},
				{title:'2018年度华为手机（含荣耀）全球发货量突破2亿，稳居全球前三。',desc:'2018年12月1日'},]" 
				direction="column" 
				:active="-1"
				active-color="#5871FE">
			</uni-steps>
			<view class="bottom_border_line"></view>
		</view>
		<!-- 公司动态 -->
		<view class="company_dynamics">
			<view class="company_profile_title">公司动态</view>
			<view class="from_industry">
				<view class="publisher_info">
					<image src="https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1894992214,3473101703&fm=58&s=9095187A4F45B20B49AA4BB70300C02D&bpow=121&bpoh=75" mode="aspectFill" class="publisher_header_img"></image>
					<view class="publisher_presentation">
						<view class="publisher_name">华为</view>
						<!-- <view class="publisher_corporation">华为技术有限公司</view> -->
					</view>
					<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" class="hidden_arrows"></image>
				</view>
				<!-- 文字展开隐藏 -->
				<view class="publish_text">营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。</view>
				<view class="publish_image">
					<image src="http://img2.imgtn.bdimg.com/it/u=334514814,3940243718&fm=26&gp=0.jpg" mode="aspectFill"></image>
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=457503980,2486741247&fm=11&gp=0.jpg" mode="aspectFill"></image>
					<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4291489099,2387855543&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
				<!-- 点赞 & 转发 & 评论 -->
				<Operation transpondNum='555' commentNum='625' likeNum="85"></Operation>
			</view>
		</view>
	</view>
</template>

<script>
	import Operation from '@/components/Operation.vue';
	import uniSteps from '@/components/uni-steps/uni-steps.vue'
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		components:{
			Operation,
			uniSteps
		}
	}
</script>

<style scoped>
	.wrapper{
		width: 100%;
	}
	.company_profile {
		width: 100%;
		padding: 50upx 33upx 0 33upx;
		box-sizing: border-box;
		background-color: #fff;
	}
	.company_profile_title {
		font-size: 34upx;
		color: #282828;
		font-weight: bold;
	}
	.company_profile_cont {
		color: #333;
		font-size: 30upx;
		margin-top: 25upx;
		line-height: 46upx;
	}
	.bottom_border {
		width: 100%;
		border-bottom: 1upx solid #e3e3e3;
		margin-top: 28upx;
	}
	.bottom_border_line {
		width: 100%;
		height: 2upx;
		background-color: #e3e3e3;
	}
	.milestone_incident {
		width: 100%;
		padding: 45upx 33upx 0 33upx;
		box-sizing: border-box;
		background-color: #fff;
	}
	.company_dynamics {
		width: 100%;
		padding: 45upx 33upx 0 33upx;
		box-sizing: border-box;
		background-color: #fff;
	}
	.from_industry {
		width: 100%;
		background-color: #fff;
	}
	.top_title {
		width: 100%;
		height: 65upx;
		color: #a6a6a8;
		font-size: 22upx;
		line-height: 65upx;
		border-bottom: 1upx solid #e3e3e3;
		padding: 0 31upx;
		box-sizing: border-box;
	}
	.publisher_info {
		width: 100%;
		padding: 29upx 0;
		box-sizing: border-box;
		display: flex;
		flex-direction: row;
	}
	.publisher_header_img {
		width: 74upx;
		height: 74upx;
		box-shadow: 0px 1upx 10upx 0px rgba(79, 125, 194, 0.2);
		border-radius: 4upx;
	}
	.publisher_presentation {
		display: flex;
		flex: 1;
		flex-direction: column;
		margin-left: 26upx;
	}
	.publisher_name {
		color: #333333;
		font-size: 30upx;
		font-weight: bold;
		margin-top: 15upx;
	}
	.publisher_corporation {
		color: #999;
		font-size: 24upx;
		margin-top: 5upx;
	}
	.publish_text {
		width: 100%;
		color: #333;
		font-size: 30upx;
		/* padding: 0 31upx;
		box-sizing: border-box; */
	}
	.hidden_arrows {
		width: 30upx;
		height: 16upx;
		margin: 10upx 0 0 10upx;
	}
	.publish_image {
		width: 100%;
		/* padding: 0 31upx;
		box-sizing: border-box; */
		display: flex;
		flex-direction: row;
		/* justify-content: space-between; */
		margin-top: 27upx;
	}
	.publish_image image {
		width: 220upx;
		height: 220upx;
		border-radius: 6upx;
		margin: 0 8upx;
	}
</style>
