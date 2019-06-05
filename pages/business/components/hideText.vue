<template>
	<div class="wrapper">
		<div class="box" ref="needBox">
			<div :class="showTrue ? 'stateMax' : 'stateMin'">{{ introduce }}</div>
			<div v-show="showFalse">
				<div v-show="showTrue ? true : false" @click="showTrue = !showTrue" class="operation_text">
					<div>展开</div>
					<image src="http://qnimage.xiteng.com/icon_arrow_down@2x.png" mode="" class="show_icon"></image>
				</div>
				<div v-show="showTrue ? false : true" @click="showTrue = !showTrue" class="operation_text">
					<div>隐藏</div>
					<image src="http://qnimage.xiteng.com/icon_arrow_up@2x.png" mode="" class="show_icon"></image>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import Vue from 'vue';
export default {
	name: 'Spread',
	data() {
		return {
			introduce: '',
			rowNumber: 0,
			showTrue: false,
			showFalse: false
		};
	},
	mounted() {
		this.init();
	},
	watch: {
		introduce() {
			let roeHeight = 30; //行高
			this.$nextTick(() => {
				this.rowNumber = this.$refs.needBox.offsetHeight / roeHeight;
				console.log('目前是', this.rowNumber, '行');
				if (this.rowNumber > 3) {
					this.showTrue = true;
					this.showFalse = true;
				} else {
					this.showFalse = false;
				}
			});
		}
	},
	methods: {
		init() {
			this.introduce =
				'华为技术有限公司创立于1987年，是全球领先的ICT（信息与通信）基础设施和智能终端提供商，我们致力于把数字世界带入每个人、每个家庭、每个组织，构建万物';
		}
	}
};
</script>

<style>
.wrapper {
	color: #333;
	font-size: 30upx;
	margin-top: 26upx;
}
.operation_text {
	width: 20%;
	text-align: center;
	color: #476aff;
	margin-top: 33upx;
	display: flex;
	flex-direction: row;
	align-items: center;
	margin: 25upx auto 0 auto;
	font-size: 30upx;
}
.stateMax {
	display: -webkit-box;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 3;
	overflow: hidden;
}
.stateMin {
	display: block;
}
.box {
	line-height: 46upx;
}
.show_icon{
	width: 30upx;
	height: 16upx;
	margin-left: 8upx;
}
</style>
