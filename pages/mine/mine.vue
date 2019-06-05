<template>
	<view class="wrapper">
		<!-- 个人简介 -->
		<view class="header_area">
			<view class="user_basic_info">
				<image src="http://img3.imgtn.bdimg.com/it/u=3519436443,202544646&fm=26&gp=0.jpg" mode="aspectFill" class="header_img"></image>
				<view class="center_cont">
					<view class="top_info_area">
						<view class="user_name">弗嵩</view>
						<view class="vip_member">
							<image src="../../static/mine/icon_vip@2x.png" class="v_icon"></image>
							<view class="vip_text">钻石会员</view>
						</view>
					</view>
					<view class="id_num">ID：3265434</view>
				</view>
				<view class="go_homepage">
					<view class="homepage_text">主页</view>
					<image src="../../static/mine/arrow_white@2x.png" class="next_icon"></image>
				</view>
			</view>
			<view class="personal_signature">大道至简，天道酬勤</view>
		</view>
		<!-- 操作列表 -->
		<view class="option_item_list">
			<optionItem itemImg="../../static/mine/me_icon_knowledge@2x.png" mainText="知识"></optionItem>
			<optionItem itemImg="../../static/mine/me_icon_circle@2x.png" mainText="圈子"></optionItem>
			<optionItem itemImg="../../static/mine/me_icon_wallet@2x.png" mainText="钱包"></optionItem>
			<optionItem itemImg="../../static/mine/me_icon_news@2x.png" mainText="消息"></optionItem>
			<optionItem itemImg="../../static/mine/me_icon_set@2x.png" mainText="设置"></optionItem>
		</view>
	</view>
</template>

<script>
	import optionItem from './components/optionItem.vue'
export default {
	data() {
		return {};
	},
	methods: {},
	components:{
		optionItem
	}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.header_area {
	width: 100%;
	height: 392upx;
	background: url('http://qnimage.xiteng.com/me_background_img.png') no-repeat center center;
	background-size: 100% 100% ;
	padding: 100upx 34upx 0 30upx;
	box-sizing: border-box;
}
.user_basic_info{
	display: flex;
	flex-direction: row;
	align-items: center;
}
.header_img{
	width: 110upx;
	height: 110upx;
	border-radius: 50%;
}
.center_cont{
	display: flex;
	flex-direction: column;
	margin-left: 32upx;
	flex: 1;
}
.top_info_area{
	display: flex;
	flex-direction: row;
	align-items: center;
}
.user_name{
	color: #FFFFFF;
	font-size: 34upx;
	margin-right: 17upx;
}
.vip_member{
	height: 33upx;
	background-color: #FFC63C;
	border-radius: 15upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	padding: 0 10upx;
	box-sizing: border-box;
}
.v_icon{
	width: 16upx;
	height: 14upx;
}
.vip_text{
	color: #FFFFFF;
	font-size: 12upx;
}
.id_num{
	color: #FFFFFF;
	font-size: 26upx;
	margin-top: 13upx;
}
.go_homepage{
	width: 100upx;
	display: flex;
	flex-direction: row;
	align-items: center;
}
.homepage_text{
	color: #FFFFFF;
	font-size: 26upx;
	margin-right: 15upx;
}
.next_icon{
	width: 18upx;
	height: 30upx;
}
.personal_signature{
	color: #FFFFFF;
	font-size: 24upx;
	margin: 50upx 0 0 140upx;
}
.option_item_list{
	width: 100%;
	padding: 0 40upx;
	box-sizing: border-box;
	margin-top: 15upx;
}
</style>
