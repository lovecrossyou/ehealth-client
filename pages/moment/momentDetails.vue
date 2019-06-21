<template>
	<view id="moments" class="wrapper">
		<view class="moments__post" v-for="(post, index) in posts" :key="index" :id="'post-' + index">
			<view class="post-left">
				<image class="post_header" :src="post.header_image" mode="aspectFill"></image>
				<text class="post-username">{{ post.username }}</text>
				<view class="timestamp">{{ post.timestamp }}</view>
			</view>

			<view class="post_right">
				<view id="paragraph" class="paragraph">{{ post.content.text }}</view>
				<!-- 相册 -->
				<view class="thumbnails">
					<view :class="post.content.images.length === 1 ? 'my-gallery' : 'thumbnail'" v-for="(image, index_images) in post.content.images" :key="index_images">
						<image class="gallery_img" lazy-load mode="aspectFill" :src="image" :data-src="image" @tap="previewImage(post.content.images, index_images)"></image>
					</view>
				</view>
				<!-- 点赞列表 -->
				<view class="give_like_list">
					<view class="give_like_details">
						<image src="http://qnimage.xiteng.com/btn_like_n@2x.png" class="give_like_icon"></image>
						<view class="give_like_num">1238</view>
					</view>
					<image src="http://img2.imgtn.bdimg.com/it/u=2233648160,3776983156&fm=26&gp=0.jpg" mode="aspectFill" class="user_img"></image>
					<image src="http://img4.imgtn.bdimg.com/it/u=1581965137,705534087&fm=26&gp=0.jpg" mode="aspectFill" class="user_img"></image>
					<image src="http://img4.imgtn.bdimg.com/it/u=2806173410,1838788200&fm=26&gp=0.jpg" mode="aspectFill" class="user_img"></image>
					<image src="http://img0.imgtn.bdimg.com/it/u=422905171,701415407&fm=26&gp=0.jpg" mode="aspectFill" class="user_img"></image>
					<image src="http://img4.imgtn.bdimg.com/it/u=2233717716,2967721208&fm=11&gp=0.jpg" mode="aspectFill" class="user_img"></image>
					<image src="http://img3.imgtn.bdimg.com/it/u=1264890844,123596423&fm=11&gp=0.jpg" mode="aspectFill" class="user_img"></image>
					<view class="more_give_like">更多</view>
				</view>
				
				<view class="post-footer">
					<!-- 评论总条数 -->
					<view class="total_discuss_list">
						<view class="discuss_text">评论</view>
						<view class="discuss_num">（99）</view>
					</view>
					<!-- 评论列表 -->
					<view class="comment_list" v-for="(comment, comment_index) in post.comments.comment" :key="comment_index" @tap="reply(index, comment_index)">
						<image :src="comment.userHeaderImg" mode="aspectFill" class="comment_user_img"></image>
						<view class="right_area">
							<view class="comment_details">
								<view class="comment_user_details">
									<view class="comment_user_name">{{comment.username}}</view>
									<view class="comment_user_company">{{comment.userCompany}}</view>
								</view>
								<view class="comment_like_details" @click="giveLike(index)" v-if="comment.isLike">
									<image src="http://qnimage.xiteng.com/btn_like_n@2x.png" class="comment_like_icon"></image>
									<view class="comment_like_num">24</view>
								</view>
								<view class="comment_like_details" @click="giveLike(index)" v-else>
									<image src="http://qnimage.xiteng.com/btn_like_s@2x.png" class="comment_like_icon"></image>
									<view class="comment_like_blue_num">24</view>
								</view>
							</view>
							<view class="comment_content">{{ comment.content }}</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 评论输入框 -->
		<view class="foot" v-show="showInput">
			<chat-input @send-message="send_comment" @blur="blur" :focus="focus" :placeholder="input_placeholder"></chat-input>
		</view>
		<view class="uni-loadmore" v-if="showLoadMore">{{ loadMoreText }}</view>
	</view>
</template>

<script>
import chatInput from './chatinput.vue'; //input框
import postData from './index.post.data.js'; //朋友圈数据

export default {
	components: {
		chatInput
	},
	data() {
		return {
			isLike:false,
			"post_id": 2,
			"uid": 1,
			"username": "华为",
			"header_image": "https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1894992214,3473101703&fm=58&s=9095187A4F45B20B49AA4BB70300C02D&bpow=121&bpoh=75",
			"content": {
				"text": "营养领域康养行业怎么发展？2019第四届中国医疗器械高峰论坛，聚焦医疗产业原材料与生产制造。",
				"images": [
					"https://clubimg.club.vmall.com/data/attachment/forum/201902/05/222326kz1xbavj9lwusnwj.jpg",
					"https://clubimg.club.vmall.com/data/attachment/forum/201902/05/222559nohzeyh1f3mvbtef.jpg",
					"https://clubimg.club.vmall.com/data/attachment/forum/201902/05/222733fflvdln16j2iohd7.jpg"
				]
			},
			"comments": {
				"total": 2,
				"comment": [{
						"uid": 2,
						isLike:false,
						"username": '张嘉',
						"userHeaderImg":'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3457127321,2708165413&fm=26&gp=0.jpg',
						"userCompany":'华为科技有限公司',
						"content": "营养领域康养行业怎么发展？"
					},
					{
						"uid": 3,
						isLike:true,
						"username": '张嘉',
						"userHeaderImg":'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3045822895,2238886242&fm=11&gp=0.jpg',
						"userCompany":'小米科技有限公司',
						"content": "2019第四届中国医疗器械高峰论坛开展。"
					},
					{
						"uid": 4,
						isLike:false,
						"username": '裔炯萨',
						"userHeaderImg":'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1539664039,2055992498&fm=26&gp=0.jpg',
						"userCompany":'华为科技有限公司',
						"content": "聚焦医疗产业原材料与生产制造。"
					}
				]
			},
			"timestamp": "1小时前",
			posts: postData, //模拟数据
			user_id: 4,
			username: 'Liuxy',

			index: '',
			comment_index: '',

			input_placeholder: '评论', //占位内容
			focus: false, //是否自动聚焦输入框
			is_reply: false, //回复还是评论
			showInput: false, //评论输入框

			screenHeight: '', //屏幕高度(系统)
			platform: '',
			windowHeight: '', //可用窗口高度(不计入软键盘)

			// loadMoreText: '加载中...',
			showLoadMore: false
		};
	},
	mounted() {
		uni.getStorage({
			key: 'posts',
			success: function(res) {
				console.log(res.data);
				this.posts = res.data;
			}
		});
	},
	onLoad() {
		uni.getSystemInfo({
			//获取设备信息
			success: res => {
				this.screenHeight = res.screenHeight;
				this.platform = res.platform;
			}
		});
		uni.startPullDownRefresh();
	},
	onShow() {
		uni.onWindowResize(res => {
			//监听窗口尺寸变化,窗口尺寸不包括底部导航栏
			if (this.platform === 'ios') {
				this.windowHeight = res.size.windowHeight;
				this.adjust();
			} else {
				if (this.screenHeight - res.size.windowHeight > 60 && this.windowHeight <= res.size.windowHeight) {
					this.windowHeight = res.size.windowHeight;
					this.adjust();
				}
			}
		});
	},
	onHide() {
		uni.offWindowResize(); //取消监听窗口尺寸变化
	},
	computed: {},
	methods: {
		giveLike(index){
			this.comments.comment[index].isLike = !this.comments.comment[index].isLike;
			console.log("11111",this.comments.comment[index].isLike)
		},
		test() {
			this.navigateTo('../test/test');
		},
		navigateTo(url) {
			uni.navigateTo({
				url: url
			});
		},
		like(index) {
			if (this.posts[index].islike === 0) {
				this.posts[index].islike = 1;
				this.posts[index].like.push({
					uid: this.user_id,
					username: ',' + this.username
				});
			} else {
				this.posts[index].islike = 0;
				this.posts[index].like.splice(
					this.posts[index].like.indexOf({
						uid: this.user_id,
						username: ',' + this.username
					}),
					1
				);
			}
		},
		comment(index) {
			this.showInput = true; //调起input框
			this.focus = true;
			this.index = index;
		},
		adjust() {
			//当弹出软键盘发生评论动作时,调整页面位置pageScrollTo
			return;
			uni.createSelectorQuery()
				.selectViewport()
				.scrollOffset(res => {
					var scrollTop = res.scrollTop;
					let view = uni.createSelectorQuery().select('#post-' + this.index);
					view.boundingClientRect(data => {
						console.log('data:' + JSON.stringify(data));
						console.log('手机屏幕高度:' + this.screenHeight);
						console.log('竖直滚动位置' + scrollTop);
						console.log('节点离页面顶部的距离为' + data.top);
						console.log('节点高度为' + data.height);
						console.log('窗口高度为' + this.windowHeight);

						uni.pageScrollTo({
							scrollTop: scrollTop - (this.windowHeight - (data.height + data.top + 45)), //一顿乱算
							// scrollTop: 50,
							duration: 300
						});
					}).exec();
				})
				.exec();
		},
		reply(index, comment_index) {
			this.is_reply = true; //回复中
			this.showInput = true; //调起input框
			let replyTo = this.posts[index].comments.comment[comment_index].username;
			this.input_placeholder = '回复' + replyTo;
			this.index = index; //post索引
			this.comment_index = comment_index; //评论索引
			this.focus = true;
		},
		blur: function() {
			this.init_input();
		},
		send_comment: function(message) {
			if (this.is_reply) {
				var reply_username = this.posts[this.index].comments.comment[this.comment_index].username;
				var comment_content = '回复' + reply_username + ':' + message.content;
			} else {
				var comment_content = message.content;
			}
			this.posts[this.index].comments.total += 1;
			this.posts[this.index].comments.comment.push({
				uid: this.user_id,
				username: this.username,
				content: comment_content //直接获取input中的值
			});
			this.init_input();
		},
		init_input() {
			this.showInput = false;
			this.focus = false;
			this.input_placeholder = '评论';
			this.is_reply = false;
		},
		previewImage(imageList, image_index) {
			var current = imageList[image_index];
			uni.previewImage({
				current: current,
				urls: imageList
			});
		},
		goPublish() {
			uni.navigateTo({
				url: './publish/publish',
				success: res => {},
				fail: () => {},
				complete: () => {}
			});
		}
	}
};
</script>

<style scoped>
@import url('./index.css');
</style>
