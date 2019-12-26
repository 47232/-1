<template>
	<view class="forget">
		<view class="forget_list">
			<input type="confirmtype" value=""  placeholder="请输入手机号"/>
		</view>
		<view class="border"></view>
		<view class="forget_list">
			<input type="confirmtype" value=""  placeholder="请输入验证码"/>
			<button class="forget_send">发送验证码</button>
		</view>
		<view class="border"></view>
		<view class="forget_list">
			<input type="confirmtype" value=""  placeholder="请输入新密码"/>
		</view>
		<view class="border"></view>
		<view class="forget_list">
			<input type="confirmtype" value=""  placeholder="请重复新密码"/>
		</view>
		<view class="border"></view>
		<view class="forget_button">
			完成
		</view>
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
			
		}
	}
</script>

<style>
	.border{
		width: 100%;
		height: 1px;
		background: #000000;
	}
	.forget {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.forget .forget_list{
		width: 90%;
		margin: 0 5%;
		height: 50px;
		display: flex;
		align-items: center;
		position: relative;
	}
	.forget_send{
		width: 24%;
		/* margin-top: 20px; */
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 12px;
		border-radius:10rpx ;
		height: 30px;
		position: absolute;
		background: #199ed8;
		right: 0;
		color: #FFFFFF;
	}
	.forget_button{
		width: 80%;
		margin-top: 20px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
		border-radius:20rpx ;
		height: 40px;
		background: #199ed8;
		color: #FFFFFF;
	}
</style>
