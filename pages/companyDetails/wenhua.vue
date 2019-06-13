<template>
	<view class="wrapper">
		<waterfallFlow></waterfallFlow>
	</view>
</template>

<script>
import waterfallFlow from '@/components/waterfallFlow/waterfallFlow.vue';
export default {
	data() {
		return {};
	},
	methods: {},
	components: {
		waterfallFlow
	},
};
</script>

<style scoped>
.wrapper {
	width: 100%;
}
</style>
