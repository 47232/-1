<template>
	<view class="invitation">
		<view class="invitation_code">
			<view class="code_tab">
				<view class="code_title">
					邀请码
				</view>
				<view class="code_tab_1">
					<view class="code_val">
						{{invitation}}
					</view>
					<view class="code_btn" @click="ctrlc">
						复制邀请码
					</view>
				</view>
			</view>
			<view class="qr_tab">
				<view class="qr_tab_1">
					<view class="qr_val">
						<image src="../../../../static/imgs/heda_cs.jpg" mode=""></image>
					</view>
					<view class="qr_btn" @click="qrcode">
						保存二维码到本地
					</view>
					<view class="qr_list">
						<text>1、保存图片到本地</text>
						<text>2、打开浏览器扫一扫</text>
					</view>
				</view>
			</view>
		</view>
		<view class="invitation_qr">

		</view>
	</view>
</template>

<script>
	// import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
	export default {
		data() {
			return {
				invitation: "123456789"
			}
		},
		onLoad() {

		},
		methods: {
			ctrlc: function() {
				uni.setClipboardData({
					data: this.invitation,
					success: function(data) {},
					fail: function(err) {},
					complete: function(res) {}
				})
			},
			// qrcode: function() {
			// 	uni.saveImageToPhotosAlbum({
			// 		filePath: res.tempFilePaths[0],
			// 		success: function() {
			// 			console.log('save success');
			// 		}
			// 	})
			// },
			qrcode: function() {
				uni.downloadFile({ // 下载图片
					url: '../../../../static/imgs/heda_cs.jpg',
					success: (res) => {
						uni.saveImageToPhotosAlbum({ // 保存图片到本地
							filePath: res.tempFilePath, // 图片临时路径
							success: function() {
								uni.showToast({
									"title": "保存成功",
									duration: 2000
								})
							},
						})
					}
				})
			}
		},
	}
</script>

<style>
	.invitation {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	page {
		background: #2487ED;

	}

	.invitation .invitation_code {
		height: 1100rpx;
		width: 100%;
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items: center;
	}

	.invitation .invitation_code .code_tab {
		width: 90%;
		height: 340rpx;
		display: flex;
		flex-direction: column;
		background: #FFFFFF;
	}

	.invitation .invitation_code .code_tab .code_title {
		height: 80rpx;
		background: #f2f2f2;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
	}

	.invitation .invitation_code .code_tab_1 {
		flex: 1;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	.invitation .invitation_code .code_tab_1 .code_val {
		height: 34px;
		width: 250rpx;
		display: flex;
		justify-content: center;
		font-size: 18px;
		font-weight: 600;
		align-items: center;
	}

	.invitation .invitation_code .code_tab_1 .code_btn {
		width: 80%;
		margin-top: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
		border-radius: 20rpx;
		height: 40px;
		background: #199ed8;
		color: #FFFFFF;
	}

	.invitation .qr_tab {
		width: 90%;
		height: 630rpx;
		background: #FFFFFF;
		display: flex;
		flex-direction: column;
	}

	.invitation .qr_tab .qr_title {
		height: 80rpx;
		background: #f2f2f2;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
	}

	.invitation .qr_tab_1 {
		flex: 1;
		display: flex;
		margin-top: 40rpx;
		/* justify-content: center; */
		align-items: center;
		flex-direction: column;
	}

	.invitation .qr_tab_1 .qr_val {
		border: 1px solid #909090;
		height: 260rpx;
		width: 318rpx;
		background: #FFFFFF;
		display: flex;
		justify-content: center;
		font-size: 14px;
		border: 10px solid #f2f2f2;
		align-items: center;
	}

	.invitation .qr_tab_1 .qr_val image {
		width: 100%;
		height: 100%;

	}

	.invitation .qr_tab_1 .qr_btn {
		width: 80%;
		margin-top: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
		border-radius: 20rpx;
		height: 40px;
		background: #199ed8;
		color: #FFFFFF;
	}

	.invitation .qr_tab_1 .qr_list {
		margin-top: 10px;
		display: flex;
		font-size: 14px;
		flex-direction: column;
	}
</style>
