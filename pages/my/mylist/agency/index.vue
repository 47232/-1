<template>
	<view class="agency">
		<view class="agency_top">
			<view class="agency_top_title">昨天</view>
			<view class="agency_top_title">今天</view>
		</view>
		<view class="agency_tab">
			<view class="agency_title">
				<text>账号</text>
				<text class="agency_right">团队业绩</text>
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
			
		}
	}
</script>

<style>
	.agency {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.agency .agency_top{
		width: 100%;
		display: flex;
		height: 40px;
		background: #2487ED;
		align-items: center;
	}
	.agency .agency_top .agency_top_title{
		height: 20px;
		width: 80px;
		/* font-size: 12px; */
		margin-left: 20px;
		color: #FFFFFF;
		background: #2487ED;
		border: 1px solid #FFFFFF;
		border-radius: 10px;
		display: flex;
		font-size: 14px;
		justify-content: center;
		align-content: center;
	}
	.agency .agency_tab{
		width: 90%;
		height: 50px;
		display: flex;
		justify-content: center;
		/* align-items: center; */
		flex-direction: column;
	}
	.agency .agency_title{
		height: 40px;
		display: flex;
		align-items: flex-end;
		position: relative;
		color: #cfdef5;
		border-bottom:1px solid #cfdef5 ;
	}
	.agency .agency_right{
		position: absolute;
		right: 0;
	}
</style>
