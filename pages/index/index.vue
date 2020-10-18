<template>
	<view style="margin-top: 200rpx;">
		<view style="margin-left: 50rpx;">
			<text>请在下方输入身份id</text>
		</view>
		<view style="margin: 50rpx;margin-top: 80rpx;">
			<view style="border: #999999 solid 1rpx; border-radius: 4rpx;padding: 12rpx;">
				<input style="margin-left: 5rpx;" confirm-type="go" id='mid' @blur="setid" :value=uid  />
			</view>
		</view>
		<view style="margin: 50rpx;margin-top: 100rpx;">
			<button style="background-color: #4CD964;" @click="gofun()">获取绿码</button>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				uid:"",
			}
		},
		methods: {
			gofun(event){
				uni.navigateTo({
					url:'../lsuPassCheck/lsuPassCheck'+'?uid='+this.uid
				})
			},
			setid(e){
					this.uid=e.target.value
					uni.setStorageSync('uid',this.uid)
			}
		},
		onLoad:function(){
			this.uid=uni.getStorageSync('uid')
		}
			
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}
</style>
