<template>
	<view class="my">
		<view class="head">
			<view class="my_portrait" @click="upimage">
				<image src="../../static/imgs/heda_cs.jpg" mode=""></image>
			</view>
			<view class="user_name">
				<text class="user_name_1">演员</text>
				<text class="user_name_2">已认证</text>
			</view>
		</view>
		<view class="number_val">
			<view class="number_tab">
				<view class="number_val_one now_pck">
					<view class="number_title">
						当前PKC
					</view>
					<view class="number_price">
						0.00
					</view>
				</view>
				<view class="number_val_one await_pck">
					<view class="number_title">
						待入PKC
					</view>
					<view class="number_price">
						0.00
					</view>
				</view>
				<view class="number_val_one earnings">
					<view class="number_title">
						今日收益
					</view>
					<view class="number_price">
						0.00
					</view>
				</view>
			</view>
		</view>
		<view class="interval">
			<view class="strip">
				
			</view>
		</view>
		<view class="device">
			<view class="device_dl"  @click="Invitation">
				<view class="device_dt">
					<image src="../../static/imgs/Invitation.png" mode=""></image>
				</view>
				<view class="device_dd">
					我的邀请码
				</view>
			</view>
			<view class="device_dl" @click="safety">
				<view class="device_dt">
					<image src="../../static/imgs/shinshop.png" mode=""></image>
				</view>
				<view class="device_dd">
					安全中心
				</view>
			</view>
			<view class="device_dl device_dl_none" @click="bank">
				<view class="device_dt">
					<image src="../../static/imgs/bank.png" mode=""></image>
				</view>
				<view class="device_dd">
					银行卡管理
				</view>
			</view>
			<view class="device_dl">
				<view class="device_dt">
					<image src="../../static/imgs/deal.png" mode=""></image>
				</view>
				<view class="device_dd">
					收款账号
				</view>
			</view>
			<view class="device_dl">
				<view class="device_dt">
					<image src="../../static/imgs/transaction.png" mode=""></image>
				</view>
				<view class="device_dd">
					交易记录
				</view>
			</view>
			<view class="device_dl device_dl_none" @click="agency">
				<view class="device_dt">
					<image src="../../static/imgs/agency.png" mode=""></image>
				</view>
				<view class="device_dd">
					代理统计
				</view>
			</view>
			<view class="device_dl" @click="khcfdc">
				<view class="device_dt">
					<image src="../../static/imgs/khcfdc.png" mode=""></image>
				</view>
				<view class="device_dd">
					佣金费率
				</view>
			</view>
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
			Invitation:function(){
				uni.navigateTo({
				    url: '/pages/my/mylist/invitation/index'
				});
			},
			safety:function(){
				uni.navigateTo({
				    url: '/pages/my/mylist/safety/index'
				});
			},
			bank:function(){
				uni.navigateTo({
					url:"/pages/my/mylist/bank/index"
				})
			},
			agency:function(){
				uni.navigateTo({
					url:"/pages/my/mylist/agency/index"
				})
			},
			khcfdc:function(){
				uni.navigateTo({
					url:"/pages/my/mylist/brokerage/index"
				})
			},
			upimage:function(){
				console.log(1233)
				uni.chooseImage({
				    count: 1,
				    sourceType: ['album'],
				    success: function (res) {
				        uni.getImageInfo({
				            src: res.tempFilePaths[0],
				            success: function (image) {
				                console.log(image);
				            }
				        });
				    }
				});
			}
		}
	}
</script>

<style>
	.my {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.my .head{
		width: 100%;
		height:320rpx;
		background: #2487ed;
		display: flex;
		align-items: center;
		flex-direction: column;
		justify-content: center;
	}
	.my .head .my_portrait{
		width: 180rpx;
		border-radius: 180rpx;
		height: 180rpx;
		background: #FFFFFF;
		border: 2rpx solid #00000;
	}
	.my .head .my_portrait image{
		width: 100%;
		height: 100%;
		border-radius: 180rpx;
	}
	.my .head .user_name{
		width: 100%;
		height: 50px;
		background: #2487ed;
		display: flex;
		align-items: center;
		flex-direction: column;
		justify-content: center;
	}
	.my .head .user_name_1{
		font-size: 16px;
		color: #FFFFFF;
		font-weight: 800;
	}
	.my .head .user_name_2{
		font-size:12px;
		color: #FFFFFF;
		font-weight: 500;
	}
	.my .number_val{
		width: 100%;
		height: 210rpx;
		background: #2487ed;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.my .number_val .number_tab{
		width: 98%;
		height: 90%;
		display: flex;
		justify-content: center;
		align-items: center;
		background: rgba(96,165,235,0.8);
		box-shadow: #F2F2F2;
		border-radius: 10px;
	}
	.my .number_val .number_val_one{
		flex: 1;
		height: 150rpx;
		/* border:1px solid #000; */
	}
	.my .number_val .number_val_one .number_title{
		font-size: 16px;
		color: #FFFFFF;
		height: 80rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	
	.my .number_val .number_val_one .number_price{
		font-size: 14px;
		color: #FFFFFF;
		display: flex;
		justify-content: center;
		align-items: center;
		justify-content: center;
	}
	.my .interval{
		width: 100%;
		height: 10px;
		display: flex;
		justify-content: center;
		align-content: center;
	}
	.my .interval .strip{
		/* margin-top: 10px; */
		width: 100%;
		height: 10px;
	}
	.my .device{
		width: 100%;
		height: auto;
		display: flex;
		flex-wrap: wrap;
		border-top:1px solid #cfdef5 ;
	}
	.my .device .device_dl{
		width: 33%;
		height: 160rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		font-weight: 600;
		
		border-right: 1px solid #cfdef5;
		border-bottom: 1px solid #cfdef5;
	}
	.my .device .device_dl image{
		width: 80rpx;
		height: 80rpx;
	}
	.my .device .device_dl_none{
		border-right:0;
	}
</style>
