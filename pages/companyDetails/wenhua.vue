<!--模板-->
<template>
	<view id="bbb">
		<view id="vm" class="pubu">
			<ul id="show" class="yg yg_l">
				<li v-for="(item, index) in ListData" :key="index" v-if="index % 2 == 0">
					<view style="position: relative"><img :src="item.e_img" alt="" mode="widthFix"/></view>
				</li>
			</ul>
			<ul class="yg yg_r">
				<li v-for="(item, index) in ListData" :key="index" v-if="index % 2 == 1">
					<view style="position: relative"><img :src="item.e_img" alt=""  mode="widthFix"/></view>
				</li>
			</ul>
			<view style="clear: both;"></view>
		</view>
	</view>
	
</template>

<script>
export default {
	data() {
		return {
			ListData: [
				{
					e_img: 'http://img4.imgtn.bdimg.com/it/u=1269541597,1719556527&fm=26&gp=0.jpg'
				},
				{
					e_img: 'http://img0.imgtn.bdimg.com/it/u=1625823568,348098948&fm=26&gp=0.jpg'
				},
				{
					e_img: 'http://img1.imgtn.bdimg.com/it/u=3893146502,314297687&fm=26&gp=0.jpg'
				},
				{
					e_img: 'http://img0.imgtn.bdimg.com/it/u=3212600922,2320351342&fm=26&gp=0.jpg'
				},
				{
					e_img: 'http://img5.imgtn.bdimg.com/it/u=3558462636,3096335901&fm=26&gp=0.jpg'
				},
				{
					e_img: 'http://img4.imgtn.bdimg.com/it/u=2150260920,11782396&fm=26&gp=0.jpg'
				}
			]
		};
	},
	methods: {
	
	},
	onLoad() {
		// this.getList();
	}
};
</script>

<!--css样式-->
<style lang="scss" scoped>
[v-cloak] {
	display: none !important;
}
* {
	padding: 0;
	margin: 0;
	list-style-type: none;
}
body {
	width: 100%;
}
.pubu {
	width: calc(100% - 16px);
	background-color: #fff;
	margin: 0 auto;
	padding-top: 20upx;
	box-sizing: border-box;
}
.yg img {
	width: 100%;
	// border-radius: 8px 8px 0 0;
}
.yg p {
	width: 100%;
	font-size: 0.75rem;
	padding: 3px;
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
	text-overflow: ellipsis;
	display: -webkit-box;
	-webkit-line-clamp: 3;
	-webkit-box-orient: vertical;
	overflow: hidden;
	color: #999;
}
.yg_l,
.yg_r {
	width: calc(50% - 5px);
}
.yg li {
	background: #fff;
}
.yg_l {
	float: left;
}
.yg_r {
	float: right;
}
.u_xinx {
	position: absolute;
	bottom: 4px;
}
.u_xinx img {
	margin-left: 5px;
	background: rgba(0, 0, 0, 0.2);
	box-shadow: 0 1px 3px rgba(0, 0, 0, 0.5);
	width: 26px;
	height: 26px;
	border-radius: 50%;
	display: inline-block;
}
.u_xinx span {
	position: relative;
	text-shadow: 0 1px 1px #333;
	top: -8px;
	color: #fff;
	font-size: 0.6rem;
}
</style>
