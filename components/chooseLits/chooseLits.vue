<template>
	<view class="boxa">
		<view class="top_kbox">
			<block v-for="(item,i) in newlist" :key="i">
				<view class="ibox" @tap="alertnum(i)" :class="[i== i1?'actives':'']">
					<text class="uni_14">{{item}}</text>
					<image v-if="i != i1" class="ii" src="http://qnimage.xiteng.com/icon_more_d@2x.png" mode=""></image>
					<image v-else class="ii" src="http://qnimage.xiteng.com/icon_more_shang@2x.png" mode=""></image>
				</view>
			</block>
		</view>
		<view  :class="[show?'list_boxs2':'list_boxs']">
			<view class="lione">
				<block v-for="(item,i) in listchild" :key="i">
					<view class="mli" @tap="chooseOne(i)">
						<text :class="[i== i2?'actives':'']" class="uni_14">{{item}}</text>
						<image v-if="i == i2" class="ii" src="/static/choose-Cade/choose-Cadecc.png" mode=""></image>
					</view>
				</block>
			</view>
			<view class="hideA" @tap="hide">
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: ['list', 'arr'], //数组  arr
		data() {
			return {
				i1: null,
				i2: null,
				show: false,
				listchild: [],
				newlist: this.list
			}
		},
		methods: {
			alertnum(i) {
				if (this.i1 != i) {
					this.listchild = [];
					this.i1 = i;
					this.listchild = this.arr[i];
					this.i2 = null;
					this.show = true;
					let ins = this.listchild.indexOf(this.newlist[i]);
					if (ins > -1) {
						this.i2 = ins
					}
				}

			},
			chooseOne(i) {
				this.i2 = i;
				this.newlist[this.i1] = this.listchild[i];
				this.$emit('chooseLike', [this.i1, this.i2]);
				this.hide()
			},
			hide() {
				this.show = false;
				this.i1 = null;
				this.i2 = null;
			}
		}
	}
</script>

<style>
	.hideA {
		height: calc(100% - 310upx);
	}

	.mli {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		padding: 25upx 50upx;
		box-sizing: border-box;
		background-color: #fff;
		border-bottom: 1upx solid #E3E3E3;
	}

	.lione {
		background-color: #fff;
		margin-top: 70upx;
		/* height: 262upx; */
		/* padding: 10upx 40upx; */

	}

	.list_boxs {
		background-color: rgba(84, 80, 80, 0.48);
		position: fixed;
		height: calc(100%);
		width: 100%;
		z-index: 88;
		transition: all .5s;
		transform: translateY(-120%);
	}
	.list_boxs2{
		background-color: rgba(84, 80, 80, 0.48);
		position: fixed;
		height: calc(100%);
		width: 100%;
		z-index: 88;
		transform: translateY(0);
		transition: all .5s;
	}

	.ii {
		width: 16upx;
		height: 16upx;
		display: block;
		margin-left: 9upx;
	}

	.actives {
		color: #F0AD4E;
	}

	.ibox {
		display: flex;
		align-items: center;
	}

	.top_kbox {
		width:100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #FFFFFF;
		box-sizing: border-box;
		position: fixed;
		top: 80upx;
		padding: 30upx 50upx 0 50upx;
		box-sizing: border-box;
		z-index: 99;
		/* #ifdef APP-PLUS */
		top: 0;
		/* #endif */
		
	}
	.boxa{
		/* padding-top: 20upx; */
	}
	.uni_14{
		color: #666666;
		font-size: 28upx;
	}
</style>
