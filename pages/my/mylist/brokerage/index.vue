<template>
	<view class="brokerage">
		<view class="brokerage_list">
			<text class="brokerage_title">
				支付宝
			</text>
			<text class="brokerage_val">
				1.10%
			</text>
		</view>
		<view class="brokerage_boder"></view>
		<view class="brokerage_list">
			<text class="brokerage_title">
				微信
			</text>
			<text class="brokerage_val">
				1.40%
			</text>
		</view>
		<view class="brokerage_boder"></view>
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
	.brokerage {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.brokerage_list{
		width: 90%;
		height: 40px;
		display: flex;
		align-items: center;
		font-size: 14px;
		position: relative;
	}
	.brokerage_val{
		position: absolute;
		right: 0px;
	}
	.brokerage_boder{
		width: 90%;
		height: 1px;
		background: #000000;
	}
</style>
