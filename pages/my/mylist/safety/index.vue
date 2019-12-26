<template>
	<view class="safety">
		<view class="safety_list" @click="real">
			<text class="safety_name">实名认证</text>
			<image src="../../../../static/imgs/next.png" mode="" class="safety_next"></image>
		</view>
		<view class="border"></view>
		<view class="safety_list" @click="amend">
			<text class="safety_name">修改登陆密码</text>
			<image src="../../../../static/imgs/next.png" mode="" class="safety_next"></image>
		</view>
		<view class="border"></view>
		<view class="safety_list"  @click="draw">
			<text class="safety_name">修改提现密码</text>
			<image src="../../../../static/imgs/next.png" mode="" class="safety_next"></image>
		</view>
		<view class="border"></view>
		<view class="safety_list"  @click="forget">
			<text class="safety_name">忘记提现密码</text>
			<image src="../../../../static/imgs/next.png" mode="" class="safety_next"></image>
		</view>
		<view class="border"></view>
		<view class="safety_list">
			<text class="safety_name">谷歌俩步验证</text>
			<image src="../../../../static/imgs/next.png" mode="" class="safety_next"></image>
		</view>
		<view class="border"></view>
		<view class="safety_list">
			<text class="safety_name">设置地区</text>
			<image src="../../../../static/imgs/next.png" mode="" class="safety_next"></image>
		</view>
		<view class="border"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
			real:function(){
				uni.navigateTo({
				    url: '/pages/my/mylist/safety/real/index'
				});
			},
			amend:function(){
				uni.navigateTo({
				    url: '/pages/my/mylist/safety/amend/index'
				});
			},
			forget:function(){
				uni.navigateTo({
				    url: '/pages/my/mylist/safety/forget/index'
				});
			},
			draw:function(){
				uni.navigateTo({
				    url: '/pages/my/mylist/safety/draw/index'
				});
			}
		}
	}
</script>

<style>
	.border{
		width: 90%;
		height: 1px;
		background: #000000;
	}
	.safety {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.safety .safety_list{
		width: 90%;
		margin: 0 5%;
		height: 50px;
		display: flex;
		align-items: center;
		position: relative;
	}
	.safety .safety_list .safety_next{
		height: 30px;
		width: 20px;
		display: flex;
		position: absolute;
		right: 0;
	}
	.safety .safety_list .safety_name{
		font-size: 14px;
	}
</style>
