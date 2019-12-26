<template>
	<view class="bank">
		<view class="bank_tab">
			<view class="bank_title">
				我的卡<text>（共2张）</text>
			</view>	
			<view class="bank_card">
				<view class="card_dl">
					<view class="card_dt">
						<text class="card_h4">建设银行</text>
						<text>储蓄卡</text>
					</view>
					<view class="card_dd">
						**** **** **** 1951
					</view>
				</view>
			</view>
			<view class="bank_card">
				<view class="card_dl">
					<view class="card_dt">
						<text class="card_h4">建设银行</text>
						<text>储蓄卡</text>
					</view>
					<view class="card_dd">
						**** **** **** 1951
					</view>
				</view>
			</view>
		</view>
		<view class="add_bank">
			添加银行卡
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
	.bank{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.bank .bank_tab{
		width: 90%;
		height: auto;
		/* background: #d7d7d7; */
		display: flex;
		flex-direction: column;
	}
	.bank .bank_tab .bank_title{
		height: 50px;
		font-size: 16px;
		/* background: #199ED8; */
		display: flex;
		/* justify-content: center; */
		align-items: center;
	}
	.bank .bank_tab .bank_title text{
		font-size: 14px;
	}
	.bank .bank_tab .bank_card{
		height: 100px;
		background: #2487ED;
		margin-bottom: 10px;
	}
	.bank .bank_tab .card_dt{
		height: 50px;
		color: #FFFFFF;
		display: flex;
		justify-content: center;
		flex-direction: column;
		padding-left: 20px;
	}
	.bank .bank_tab .card_h4{
		font-size: 16px;
	}
	.bank .bank_tab .card_dd{
		font-size: 24px;
		padding-left: 20px;
		color: #FFFFFF;
	}
	.bank .add_bank{
		margin-top: 50px;
		width: 60%;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 18px;
		border-radius: 20px;
		height: 50px;
		color: #FFFFFF;
		background: #2487ED;
	}
</style>
