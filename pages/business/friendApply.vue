<template>
	<view class="wrapper">
		<block v-for="(items,index) in friendApplyList" :key="index">
			<view class="friend_apply_list">
				<image :src="items.userHeaderImg" mode="aspectFill" class="header_img"></image>
				<view class="center_cont">
					<view class="friends_name">{{items.name}}</view>
					<view class="friends_info">
						<view class="friend_occupation">{{items.post}}</view>
						<view>{{items.companyName}}</view>
					</view>
				</view>
				<view class="add_friend_btn">加好友</view>
			</view>
		</block>
	</view>
</template>

<script>
export default {
	data() {
		return {
			friendApplyList:[
				{
					name: '阿豪',
					userHeaderImg: 'http://img4.imgtn.bdimg.com/it/u=24119337,1902824881&fm=26&gp=0.jpg',
					post: '产品经理',
					companyName: '小米科技有限公司'
					// http://img1.imgtn.bdimg.com/it/u=4074166390,3495936967&fm=26&gp=0.jpg
				},{
					name: '安静',
					userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=4074166390,3495936967&fm=26&gp=0.jpg',
					post: '人事专员',
					companyName: '鑫盛泓腾文化发展有限公司'
				},{
					name: '曹正',
					userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=114119863,368751066&fm=26&gp=0.jpg',
					post: '行政主管',
					companyName: '艺竹林美容中心'
				},{
					name: '康志成',
					userHeaderImg: 'http://img2.imgtn.bdimg.com/it/u=2010954630,4187517264&fm=26&gp=0.jpg',
					post: '手术室护士',
					companyName: '仁爱万家健康管理有限公司'
				},{
					name: '孟强',
					userHeaderImg: 'http://img4.imgtn.bdimg.com/it/u=4178807172,2583465338&fm=26&gp=0.jpg',
					post: '经理助理',
					companyName: '格力电子商务有限公司'
				},
			]
		};
	},
	methods: {}
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
.friend_apply_list {
	width: 100%;
	height: 140upx;
	display: flex;
	flex-direction: row;
	padding: 30upx 50upx;
	box-sizing: border-box;
	align-items: center;
	background-color: #fff;
	margin-top: 10upx;
}
.header_img {
	width: 80upx;
	height: 80upx;
	border-radius: 10upx;
}
.center_cont {
	flex: 1;
	margin-left: 25upx;
}
.friends_name {
	color: #333;
	font-size: 30upx;
}
.friends_info {
	display: flex;
	flex-direction: row;
	color: #999;
	font-size: 24upx;
	margin-top: 10upx;
}
.friend_occupation {
	margin-right: 15upx;
}
.add_friend_btn {
	width: 111upx;
	height: 49upx;
	background: #5871fe;
	border-radius: 4upx;
	color: #ffffff;
	font-size: 26upx;
	text-align: center;
	line-height: 49upx;
	font-weight: 400;
}
</style>
