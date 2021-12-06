<template>
	<view class="content">
		<image class="logo" src="/static/logo.png" @click="go"></image>
		<view class="text-area">
			<text class="title">js-xlsx:https://www.npmjs.com/package/js-xlsx</text>
			<text>点击图片</text>
			<!-- <excel @getResult="getMyExcelData1"></excel> -->
		</view>

		
	</view>
</template>

<script>
	import excel from "../../components/excelread.vue"
	export default {
		components:{
			excel
		},
		data() {
			return {
				title: 'Hello',
				src: ""
			}
		},
		onLoad() {
			
		},
		methods: {
			handleMessage(e) {
				console.log(e, "拿到的数据")
			},
			go(){
				uni.navigateTo({
					url:'../webview'
				})
			},
			getMyExcelData1(data,datahtml){
				console.log(data)
				console.log(datahtml)
			}
		}
	}
</script>

<style>
	.content {
		width: 100vw;
		height: 100vh;
	}

	.web {
		width: 100vw;
		height: 200rpx;
		background-color: red;
	}
</style>
