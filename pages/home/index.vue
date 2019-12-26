<template>
	<view class="home">
		<view class="phone" v-if="!if_show_1" @click="btn_show_1()">
		  <div class="outer">
		          <div class="inner"></div>
		      </div>
		  <view class="btn_text_1">正在抢单</view>
		</view>
	<view class="anniu" v-show="if_show_1">
		<view class="anniu_btn" @click="btn_show">
			<view class="btn_text">开始抢单</view>
		</view>
	</view>
</view>
</template>

<script>
	
	export default {
		data() {
			return {
				if_show_1:true
			}
		},
		onLoad() {

		},
		methods: {
			btn_show:function  () {
				this.if_show_1=false
			},
			btn_show_1:function(){
				this.if_show_1=true
			}
		}
	}
</script>

<style>
	@import "../../common/style.css";
	.home {
		flex: 1;
		display: flex;
		flex-direction: column;
		overflow: auto;
		align-items: center;
		justify-content: center;
	}
	page{
		background: #102671;
		height: 100%;
		width: 100%;
		display: flex;
	}
	.anniu{
		height: 100%;
		width: 100%;
		background: #FFFFFF;
		display: flex;
		justify-content: center;
		align-content: center;
	}
	.anniu_btn{
		margin-top: 60px;
		width: 330rpx;
		height: 330rpx;
		display: flex;
		justify-content: center;
		align-content: center;
		border: 10px solid #199ED8;
		border-radius: 50%;
		background: #2487ED;
		color: #FFFFFF;
		position: relative;
	}

	.anniu_btn .btn_text{
		position: absolute;
		top: 50px;
		font-size: 30px;
		display: flex;
		justify-content: center;
		align-content: center;
	}
</style>
