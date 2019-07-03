<template>
	<view class="wrapper"><phone-directory :phones="phones" @paramClick="paramClick"></phone-directory></view>
</template>

<script>
import phoneDirectory from './components/phone-directory/phone-directory.vue';
export default {
	name: 'phones',
	components: {
		phoneDirectory
	},
	data() {
		return {
			//示例数据
			phones: {
				A: [
					{
						id: 56,
						spell: 'ahao',
						name: '阿豪',
						userHeaderImg: 'http://img4.imgtn.bdimg.com/it/u=24119337,1902824881&fm=26&gp=0.jpg',
						post: '产品经理',
						companyName: '小米科技有限公司'
					},
					{
						id: 57,
						spell: 'anjing',
						name: '安静',
						userHeaderImg: 'http://img0.imgtn.bdimg.com/it/u=2329947146,719483020&fm=26&gp=0.jpg',
						post: '人事专员',
						companyName: '北京鑫盛泓腾文化发展有限公司'
					},
					{
						id: 58,
						spell: 'angel',
						name: 'Angel',
						userHeaderImg: 'http://img2.imgtn.bdimg.com/it/u=3501628132,525071476&fm=26&gp=0.jpg',
						post: '销售助理',
						companyName: '北京乐享阅读教育科技有限责任公司'
					},
					{
						id: 59,
						spell: 'aili',
						name: '爱丽',
						userHeaderImg: 'http://img4.imgtn.bdimg.com/it/u=1035315321,3787678469&fm=26&gp=0.jpg',
						post: '产品经理',
						companyName: '小米科技有限公司'
					},
					{
						id: 60,
						spell: 'ailun',
						name: '艾伦',
						userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=2006358511,976316982&fm=26&gp=0.jpg',
						post: '经理助理/秘书',
						companyName: '北京格力电子商务有限公司'
					},
					{
						id: 338,
						spell: 'acheng',
						name: '阿城',
						userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=201074510,3034021613&fm=26&gp=0.jpg',
						post: '3/4GRF优化工程师',
						companyName: '移电联通信技术有限公司'
					},
					{
						id: 340,
						spell: 'anji',
						name: '安吉',
						userHeaderImg: 'http://img3.imgtn.bdimg.com/it/u=2673351700,3173881551&fm=26&gp=0.jpg',
						post: '华为中高级工程师',
						companyName: '华为科技有限公司'
					},
					{
						id: 345,
						spell: 'anyuan',
						name: '安远',
						userHeaderImg: 'http://t8.baidu.com/it/u=837873295,376731769&fm=191&app=48&size=h300&n=0&g=4n&f=JPEG?sec=1853310920&t=57a8fee278303954acacb18f9b134240',
						post: '产品经理',
						companyName: '小米科技有限公司'
					}
				],
				B: [
					{
						id: 1,
						spell: 'beibie',
						name: '贝贝',
						userHeaderImg: 'http://img3.imgtn.bdimg.com/it/u=3076911887,1282110692&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					},
					{
						id: 591,
						spell: 'balu',
						name: '八路',
						userHeaderImg: 'http://img3.imgtn.bdimg.com/it/u=3803605038,2652056731&fm=11&gp=0.jpg',
						post: '产品经理',
						companyName: '小米科技有限公司'
					},
					{
						id: 610,
						spell: 'baifeifei',
						name: '白飞飞',
						userHeaderImg: 'http://img0.imgtn.bdimg.com/it/u=515499047,546698719&fm=26&gp=0.jpg',
						post: '经理助理/秘书',
						companyName: '北京格力电子商务有限公司'
					},
					{
						id: 138,
						spell: 'bisiyu',
						name: '毕思雨',
						userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=201074510,3034021613&fm=26&gp=0.jpg',
						post: '行政主管',
						companyName: '艺竹林美容中心'
					}
				],
				C: [
					{
						id: 22,
						spell: 'caozheng',
						name: '曹正',
						userHeaderImg: 'http://img1.imgtn.bdimg.com/it/u=114119863,368751066&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					},
					{
						id: 592,
						spell: 'chenhong',
						name: '陈宏',
						userHeaderImg: 'http://img3.imgtn.bdimg.com/it/u=3803605038,2652056731&fm=11&gp=0.jpg',
						post: '产品经理',
						companyName: '小米科技有限公司'
					},
					{
						id: 620,
						spell: 'cuijie',
						name: '崔杰',
						userHeaderImg: 'http://img0.imgtn.bdimg.com/it/u=515499047,546698719&fm=26&gp=0.jpg',
						post: '经理助理/秘书',
						companyName: '北京格力电子商务有限公司'
					},
					{
						id: 128,
						spell: 'chenli',
						name: '陈丽',
						userHeaderImg: 'http://img3.imgtn.bdimg.com/it/u=2433230368,1991650479&fm=11&gp=0.jpg',
						post: '行政主管',
						companyName: '艺竹林美容中心'
					}
				],
				K: [
					{
						id: 253,
						spell: 'kunming',
						name: '康康',
						userHeaderImg: 'http://img2.imgtn.bdimg.com/it/u=2233053717,3137329593&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					},
					{
						id: 134,
						spell: 'kangjunli',
						name: '康俊丽',
						userHeaderImg: 'http://img0.imgtn.bdimg.com/it/u=3692084460,3788563900&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					},
					{
						id: 375,
						spell: 'kangzhicheng',
						name: '康志成',
						userHeaderImg: 'http://img2.imgtn.bdimg.com/it/u=2010954630,4187517264&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					}
				],
				M: [
					{
						id: 203,
						spell: 'mengqiang',
						name: '孟强',
						userHeaderImg: 'http://img4.imgtn.bdimg.com/it/u=4178807172,2583465338&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					},
					{
						id: 204,
						spell: 'mingming',
						name: '明明',
						userHeaderImg: 'http://img3.imgtn.bdimg.com/it/u=1479509131,2407386668&fm=26&gp=0.jpg',
						post: '手术室护士',
						companyName: '仁爱万家健康管理有限公司'
					}
				]
			}
		};
	},
	methods: {
		paramClick(e) {
			console.log(this.phones);
		}
	}
};
</script>

<style>
.wrapper {
}
</style>
