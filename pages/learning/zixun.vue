<template>
	<div class="main">
		<view class="nav-title-wrapper">
			<naviTitle title="项目分类"></naviTitle>
		</view>
		<view class="projects">
			<view class="project-item">
				<image class="project-item-image" src="../../static/learn/zixun/one.png"></image>
				<view class="project-item-name">
					康养地产
				</view>
			</view>

			<view class="project-item">
				<image class="project-item-image" src="../../static/learn/zixun/two.png"></image>
				<view class="project-item-name">
					康养信息化
				</view>
			</view>

			<view class="project-item">
				<image class="project-item-image" src="../../static/learn/zixun/three.png"></image>
				<view class="project-item-name">
					康养大数据
				</view>
			</view>

			<view class="project-item">
				<image class="project-item-image" src="../../static/learn/zixun/four.png"></image>
				<view class="project-item-name">
					康养融合
				</view>
			</view>

			<view class="project-item">
				<image class="project-item-image" src="../../static/learn/zixun/five.png"></image>
				<view class="project-item-name">
					康养生态
				</view>
			</view>

			<view class="project-item">
				<image class="project-item-image" src="../../static/learn/zixun/six.png"></image>
				<view class="project-item-name">
					康养服务
				</view>
			</view>
		</view>


		<view class="nav-title-wrapper">
			<naviTitle title="推荐机构"></naviTitle>
			<view class="recommands">
				<view class="item-wrapper">
					<image class="recommand-item-1" src="../../static/learn/zixun/seven.png"></image>
					<view class="recommand-item-wrapper">
						<view class="recommand-title">
							北京康养产业研究院
						</view>
						<view class="recommand-desc">
							咨询项目：294个
						</view>
					</view>
				</view>


				<view class="recommands-row">
					<view class="item-wrapper">
					<image class="recommand-item-2" src="../../static/learn/zixun/eight.png"></image>
					<view class="recommand-item-wrapper">
						<view class="recommand-title">
							北京康养产业研究院
						</view>
						<view class="recommand-desc">
							咨询项目：294个
						</view>
					</view>
				</view>
				
				<view class="item-wrapper">
					<image class="recommand-item-3" src="../../static/learn/zixun/nine.png"></image>
					<view class="recommand-item-wrapper">
						<view class="recommand-title">
							北京康养产业研究院
						</view>
						<view class="recommand-desc">
							咨询项目：294个
						</view>
					</view>
				</view>
					
					<!-- <image class="recommand-item-2" src="../../static/learn/zixun/eight.png">
						<view class="recommand-title">
							泰康康养服务中心
						</view>
						<view class="recommand-desc">
							咨询项目：294个
						</view>
					</image>
					<image class="recommand-item-3" src="../../static/learn/zixun/nine.png">
						<view class="recommand-title">
							国家检测中心
						</view>
						<view class="recommand-desc">
							咨询项目：294个
						</view>
					</image> -->
					
					
				</view>
			</view>
		</view>

		<view class="nav-title-wrapper">
			<naviTitle title="经典项目案例"></naviTitle>
		</view>

		<view class="p-examples">
			<view class="p-example">
				<image class="p-example-image"></image>
				<view class="p-example-title">
					第四届中国康养高峰论坛承办
				</view>
				<view class="p-example-time">
					开始时间：2019年3月10日
				</view>
			</view>
			<view class="p-example">
				<image class="p-example-image"></image>
				<view class="p-example-title">
					第四届中国康养高峰论坛承办
				</view>
				<view class="p-example-time">
					开始时间：2019年3月10日
				</view>
			</view>

			<view class="p-example">
				<image class="p-example-image"></image>
				<view class="p-example-title">
					第四届中国康养高峰论坛承办
				</view>
				<view class="p-example-time">
					开始时间：2019年3月10日
				</view>
			</view>
		</view>
	</div>
</template>

<script>
	import naviTitle from "@/components/navi-title.vue";
	export default {
		components: {
			naviTitle
		},
	}
</script>

<style>
	.nav-title-wrapper {
		padding: 0 20upx 23upx 20upx;
		background-color: #FFFFFF;
	}

	.p-examples {
		padding: 20upx;
		background: #FFFFFF;
		margin-bottom: 9upx;
	}

	.p-example {
		position: relative;
	}

	.p-example-image {
		width: 160upx;
		height: 160upx;
		border-radius: 10upx;
		background-color: #0081FF;
	}

	.p-example-title {
		width: 388px;
		font-size: 30upx;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: rgba(51, 51, 51, 1);
		line-height: 44upx;

		position: absolute;
		left: 192upx;
		top: 20px
	}

	.p-example-time {
		font-size: 26upx;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: rgba(153, 153, 153, 1);
		line-height: 44upx;
		position: absolute;
		left: 192upx;
		bottom: 20px
	}

	.projects {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-between;
		padding: 0 30upx;
		box-sizing: border-box;

	}

	.project-item {
		width: 216upx;
		height: 130upx;

		/* background: rgba(12, 17, 35, 1); */
		opacity: 0.64;
		border-radius: 10upx;
		margin-bottom: 25upx;
		position: relative;


		display: flex;
		justify-content: center;
		align-items: center;
	}

	.item-wrapper {
		position: relative;
	}

	.recommand-item-1 {
		width: 690upx;
		height: 240upx;
		border-radius: 10upx;
		/* background: #0081FF; */
		margin-left: 10upx;

		/* position: relative; */
	}

	.recommand-item-wrapper {
		position: absolute;
		bottom: 30upx;
		left: 30upx;
		width: 100%;
		/* height: 60upx; */
		/* background-color: #0081FF; */
	}

	.recommand-title {
		/* position: absolute;
		left: 30upx;
		bottom: 70upx; */
		color: #FFFFFF;
		font-size: 30upx;
		margin-bottom: 10upx;

	}

	.recommand-desc {

		color: #FFFFFF;
		font-size: 24upx;
	}

	.recommands-row {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 0 10upx;
		box-sizing: border-box;
		margin-top: 10upx;
	}

	.recommand-item-2 {
		width: 335upx;
		height: 200upx;
		border-radius: 10upx;
		/* background: #0081FF; */
		margin: auto;
		position: relative;
	}

	.recommand-item-3 {
		width: 335upx;
		height: 200upx;
		border-radius: 10upx;
		/* background: #0081FF; */
		margin: auto;
		position: relative;
	}

	.project-item-image {
		position: absolute;
		left: 0;
		right: 0;
		width: 216upx;
		height: 130upx;
	}

	.project-item-name {
		color: #FFFFFF;
		font-size: 32upx;
	}
</style>
