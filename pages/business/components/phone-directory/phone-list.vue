<template>
	<view class="wrapper_padding">
		<scroll-view
			class="scroll-list"
			:scroll-top="1"
			scroll-y="true"
			:scroll-with-animation="scrollAnimationOFF"
			:scroll-into-view="scrollViewId"
			:style="{ height: winHeight + 'px' }"
			@scroll="handleScroll"
		>
			<view class="phone-list">
				<view class="list-item" v-for="(item, key) of phones" :key="key" :id="key">
					<view class="list-item-title">{{ key }}</view>
					<view
						class="list-item-phone"
						@click="handleClick"
						hover-class="commonly-hover"
						:hover-start-time="20"
						:hover-stay-time="70"
						v-for="innerItem in item"
						:key="innerItem.id"
						:data-name="innerItem.name"
						:data-id="innerItem.id"
						:data-phoneNumber="innerItem.phoneNumber"
					>
						<image :src="innerItem.userHeaderImg " mode="aspectFill" class="user_header_img"></image>
						<view class="right_info">
							<view class="friends_name">{{innerItem.name}}</view>
							<view class="friends_company">
								<view class="friends_post">{{innerItem.post}}</view>
								<view class="friends_company_name">{{innerItem.companyName}}</view>
							</view>
						</view>
						
					</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
export default {
	name: 'phone-list',
	props: {
		phones: Object,
		letter: String,
		scrollAnimationOFF: Boolean
	},
	data() {
		return {
			winHeight: 0,
			scrollTop: 0,
			letterDetails: [],
			timer: null
		};
	},
	computed: {
		scrollViewId() {
			return this.letter;
		}
	},
	mounted() {
		// #ifndef APP-PLUS
		this.winHeight = uni.getSystemInfoSync().windowHeight - 49.5;
		//#endif

		//#ifdef APP-PLUS
		this.winHeight = uni.getSystemInfoSync().windowHeight - 100;
		//#endif
	},
	methods: {
		handleClick(e) {
			this.$emit('handleClick', e.target.dataset);
		},
		handleScroll(e) {
			if (this.letterDetails.length === 0) {
				let view = uni.createSelectorQuery().selectAll('.list-item');
				view.boundingClientRect(data => {
					let top = data[0].top;
					data.forEach((item, index) => {
						item.top = item.top - top;
						item.bottom = item.bottom - top;
						this.letterDetails.push({
							id: item.id,
							top: item.top,
							bottom: item.bottom
						});
					});
				}).exec();
			}

			const scrollTop = e.detail.scrollTop;
			this.letterDetails.some((item, index) => {
				if (scrollTop >= item.top && scrollTop <= item.bottom - 5) {
					this.$emit('change', item.id);
					this.$emit('reset', true);
					return true;
				}
			});
		}
	}
};
</script>

<style>
.wrapper_padding {
	width: 100%;
	padding: 0 31upx;
	box-sizing: border-box;
}
.commonly-hover {
	background-color: #eee;
}

.scroll-list {
	flex: 1;
	height: 100vh;
	overflow-y: hidden;
}

.phone-list {
	display: flex;
	background-color: #fff;
	flex-direction: column;
	position: relative;
	width: 100%;
}

.list-item {
	width: 100%;
	display: flex;
	align-items: center;
	flex-wrap: wrap;
	height: 92upx;
	background-color: #fff;
	height: 100%;
}
.list-item-phone{
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
.list-item > .list-item-phone {
	font-weight: normal;
}

.list-item-title {
	background-color: #fff;
}

.list-item-title {
	width: 100%;
	height: 92upx;
	line-height: 92upx;
	color: #333;
	font-size: 30upx;
	font-weight: bold;
	padding: 0 20upx;
	box-sizing: border-box;
}
</style>
