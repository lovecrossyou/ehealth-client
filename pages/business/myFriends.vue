<template>
	<view class="wrapper">
		<web-view src="http://192.168.1.246:8002/#/articleDetail?article_id=5d1b0e35fa2b8b09b0b7431e" :webview-styles="webviewStyles"></web-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				 webviewStyles: {
					 width:'100%',
					 background:'pink',
                    progress: {
                       
                    }
                }
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	.wrapper{
		width: 100%;
	}
</style>
