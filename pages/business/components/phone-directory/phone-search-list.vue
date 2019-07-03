<template>
	<view>
		<!-- 搜索框 -->
		<view class="phone-main-search">
			<navigator :url="'phoneSearch?phones=' + phonesEscape" hover-class="none" class="search_area">
				<image src="http://qnimage.xiteng.com/icon_search@2x.png" mode="" class="search_icon"></image>
				<input @input="handleInput" class="search-input" type="text" focus placeholder="搜索公司、人名、职位" />
			</navigator>
		</view>
		<view class="search-main" v-if="keyword">
			<view class="search-main-errtitle" v-if="hasNoData">无搜索结果</view>
			<view
				class="search-main-title"
				hover-class="hover"
				@click="handleClick"
				:hover-start-time="20"
				:hover-stay-time="70"
				v-for="item of list"
				:key="item.id"
				:data-name="item.name"
				:data-id="item.id"
				:data-phoneNumber="item.phoneNumber"
			>
				<image src="http://img0.imgtn.bdimg.com/it/u=395993443,4184879103&fm=26&gp=0.jpg" mode="aspectFill" class="user_header_img"></image>
				<view class="right_info">
					<view class="friends_name">{{ item.name }}</view>
					<view class="friends_company">
						<view class="friends_post">产品经理</view>
						<view class="friends_company_name">小米科技有限公司</view>
					</view>
				</view>
				
			</view>
		</view>
	</view>
</template>

<script>
export default {
	name: 'phone-search-list',
	props: {
		phones: Object
	},
	data() {
		return {
			keyword: '',
			list: [],
			timer: null
		};
	},
	computed: {
		hasNoData() {
			return !this.list.length;
		},
		phonesEscape () {
			return escape(JSON.stringify(this.phones))
		}
	},
	watch: {
		keyword() {
			if (this.timer) {
				clearTimeout(this.timer);
			}
			if (!this.keyword) {
				this.list = [];
				return;
			}
			this.timer = setTimeout(() => {
				const result = [];
				for (let i in this.phones) {
					this.phones[i].forEach(item => {
						if (item.spell.indexOf(this.keyword) > -1 || item.name.indexOf(this.keyword) > -1) {
							result.push(item);
						}
					});
				}
				this.list = result;
			}, 100);
		}
	},
	methods: {
		handleInput(e) {
			this.keyword = e.detail.value;
		},
		handleClick(e) {
			this.$emit('paramClick', e.target.dataset);
		}
	}
};
</script>

<style>
.hover {
	background-color: #eee;
}
.search-main {
	height: 100%;
	padding-bottom: 20upx;
	background-color: #fff;
	overflow: hidden;
}
.search-main-title{
	width: 100%;
	/* height: 92upx; */
	padding: 20upx 15upx;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	align-items: center;
	/* border-bottom: 1upx solid pink; */
}
.user_header_img{
	width:80upx;
	height:80upx;
	border-radius:10upx;
}
.right_info{
	display: flex;
	flex-direction: column;
	margin-left: 25upx;
}
.friends_name{
	color: #333;
	font-size: 30upx;
}
.friends_company{
	color: #999;
	font-size: 24upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin-top: 10upx;
}
.friends_post{
	margin-right: 13upx;
}
.search-main-errtitle{
	width: 100%;
	height: 92upx;
	line-height: 92upx;
	font-size: 32upx;
	padding: 0 20upx;
	border-bottom: 1px solid #e5e5e5;
	color: #333333;
	font-size: 30upx;
}
.phone-main-search {
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
	width: 689upx;
	height: 64upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	background-color: #f5f4f4;
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
.phone-main-input {
	flex: 1;
	height: 31upx;
	background-color: #f5f4f4;
	color: #999999;
	font-size: 26upx;
}
</style>
