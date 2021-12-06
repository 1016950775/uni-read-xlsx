<template>
	<view class="window">
		<view class="cont" v-if="xldata" v-html="xldata">
			
		</view>
		<web-view v-if="!xldata" :src="src" @message="handleMessage"></web-view>
		<!-- <web-view src="http://192.168.1.23:8081/" @message="handleMessage"></web-view> -->
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src:"",
				xldata:""
			}
		},
		onLoad() {
			console.log(123)
			setTimeout(()=>{
				console.log(456)
				this.src = "/hybrid/html/index.html"
			},1000)
		},
		methods: {
			handleMessage(e) {
				console.log(e, "拿到的数据")
				this.xldata  = e.detail.data[0].info
			},
		}
	}
</script>

<style>
.window{
	width: 100vw;
	height: 100vh;
}
</style>
