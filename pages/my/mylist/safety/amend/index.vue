<template>
	<view class="amend">
		<view class="amend_list">
			<input type="confirmtype" value=""  placeholder="请输入旧密码"/>
		</view>
		<view class="border"></view>
		<view class="amend_list">
			<input type="confirmtype" value=""  placeholder="请输入新密码"/>
		</view>
		<view class="border"></view>
		<view class="amend_list">
			<input type="confirmtype" value=""  placeholder="请重复新密码"/>
		</view>
		<view class="border"></view>
		<view class="amend_button">
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
	.amend {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.amend .amend_list{
		width: 90%;
		margin: 0 5%;
		height: 50px;
		display: flex;
		align-items: center;
		position: relative;
	}
	.amend_button{
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
