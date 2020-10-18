<template>
	<view>
		 <view style="margin-top: 13rpx;">
		       <image :src="myimg" style="width: 100%;" ></image>
		 </view>
		 <view style="text-align: center;margin-top: 40rpx;">
			 <text id="mytime" style="font-size: 60rpx;" >{{ mytime }}</text> 
		 </view>
		 <view style="margin-top: 30rpx;text-align: center;">
		       <image :src="myma" style="width: 400rpx;height: 400rpx;"  ></image> 
		 </view>
		 <view style="text-align: center;">
			 <text>(校园通信码: 绿码允许, 红码禁止)</text>
		 </view>
	</view>
</template>

<script>
	
	
	export default {
		data() {
			return {
				myimg:"",
				mytime:"",
				myma:"https://team.shuaigeek.cn/jkm.jpg"
			}
		},
		methods: {
		
	
		},
		
		onLoad(options) {
			
			uni.setNavigationBarTitle({
				title:options.title
			}),		
			this.myimg="https://team.shuaigeek.cn/stu/"+options.uid+'.jpg'
			,setInterval(()=>{
				var date = new Date();
				var y = date.getFullYear();
				var m = date.getMonth() + 1;
				m = m < 10 ? ('0' + m) : m;
				var d = date.getDate();
				d = d < 10 ? ('0' + d) : d;
				var h = date.getHours();
				h = h < 10 ? ('0' + h) : h;
				var minute = date.getMinutes();
				var second = date.getSeconds();
				minute = minute < 10 ? ('0' + minute) : minute;
				second = second < 10 ? ('0' + second) : second;
				this.mytime=m+"月"+d+"日  "+h+":"+minute+":"+second;

			},1000)
	
		},
		
	}
</script>

<style>

</style>
