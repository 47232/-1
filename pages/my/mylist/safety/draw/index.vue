<template>
	<view class="draw">
		<view class="draw_list">
			<input type="confirmtype" value=""  placeholder="请输入旧提现密码"/>
		</view>
		<view class="border"></view>
		<view class="draw_list">
			<input type="confirmtype" value=""  placeholder="请输入新提现密码"/>
		</view>
		<view class="border"></view>
		<view class="draw_list">
			<input type="confirmtype" value=""  placeholder="请重复新提现密码"/>
		</view>
		<view class="border"></view>
		<view class="draw_button">
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
	.draw{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.draw .draw_list{
		width: 90%;
		margin: 0 5%;
		height: 50px;
		display: flex;
		align-items: center;
		position: relative;
	}
	.draw_button{
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
