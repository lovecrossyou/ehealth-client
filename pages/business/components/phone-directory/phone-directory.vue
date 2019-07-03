<template>
	<view class="phone-main" :style="{height: winHeight + 'px'}">
		<!-- 搜索框 -->
		<view class="phone-main-search">
			<navigator :url="'phoneSearch?phones=' + phonesEscape" hover-class="none" class="search_area">
			<!-- <view class="search_area"> -->
				<image src="http://qnimage.xiteng.com/icon_search@2x.png" mode="" class="search_icon"></image>
				<input disabled="false" class="phone-main-input" type="text" placeholder="搜索公司、人名、职位"/>
			<!-- </view> -->
			</navigator>
		</view>
		<view class="phoneDirectory">
			<phone-list 
			:phones="phones" 
			:letter="letter"
			:scrollAnimationOFF="scrollAnimationOFF" 
			@change="handlePhoneListIndex"
			@reset="handleReset"
			@handleClick="handleClick"
			>
			</phone-list>
			<phone-alphabet 
			:phones="phones"
			:phoneListIndex="phoneListIndex"
			@change="handleDatasetKey" 
			@scrollAnimationOFF="handleScrollAnimationOFF"
			@reset="handleReset"
			>
			</phone-alphabet>
		</view>
	</view>
</template>

<script>
	import phoneList from './phone-list.vue'
	import phoneAlphabet from './phone-alphabet.vue'
	
	export default {
		name:"phone-directory",
		components:{
			phoneList,
			phoneAlphabet
		},
		props:{
			phones:Object,
			default:false
		},
		data () {
			return {
				winHeight:0,
				letter : 'A',
				scrollAnimationOFF:true,
				phoneListIndex:'A',
				reset:true
			}
		},
		computed:{
			phonesEscape () {
				return escape(JSON.stringify(this.phones))
			}
		},
		mounted () {
			let windowHeight = uni.getSystemInfoSync().windowHeight
			
			// #ifndef APP-PLUS
			this.winHeight = windowHeight
			//#endif
			
			//#ifdef APP-PLUS
			this.winHeight = windowHeight - 56
			//#endif
			
 			if(!this.phones){
				uni.showToast({
					title: '没有数据',
					icon:"none",
					mask: false,
					duration: 1500
				})
			}
		},
		methods:{
			handleClick (e) {
				this.$emit('paramClick',e)
			},
			handleDatasetKey (val) {
				this.letter = val
			},
			handleScrollAnimationOFF (val) {
				this.scrollAnimationOFF = val
			},
			handlePhoneListIndex(val){
				if(this.reset){
					this.phoneListIndex = val
				}
			},
			handleReset (val){
				if(val){
					this.letter = ''
				}
				this.reset = val
			}
			
		}
	}
</script>

<style>
.phone-main{
	display: flex;
	flex-direction: column;
	overflow: hidden;
}
.phoneDirectory{
	display: flex;
	flex-direction: row;
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
