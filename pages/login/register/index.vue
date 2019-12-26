<template>
	<view class="register">
		<uni-popup ref="popup" type="center" class="popup_style">{{align}}</uni-popup>
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="请输入邀请码" class="register_account" v-model="Invitationc"
			 placeholder-class="place" />
		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="请设置用户名" class="register_account" v-model="username"
			 placeholder-class="place" />
		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="请设置账号(至少8位字符账号)" class="register_account" v-model="name"
			 placeholder-class="place" />
		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="请输入手机号" class="register_account" placeholder-class="place" v-model="phone" />
		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="请输入验证码" class="register_account_1" placeholder-class="place" v-model="vercode" />
			<view class="register_title">
				<image src="http://139.159.158.208/api/v1/captcha" alt="">
			</view>
		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="设置密码(8-20位数字及字母组合密码)" class="register_account" placeholder-class="place"
			 v-model="password" />

		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_tab">
			<input type="confirmtype" value="" placeholder="请第二次输入密码" class="register_account" placeholder-class="place" />
		</view>
		<view class="correct"></view>
		<!-- <view class="mistake"></view> -->
		<view class="register_button" @click="gologin">
			注册
		</view>
	</view>
</template>

<script>
	import uniPopup from "../../../components/uni-popup/uni-popup.vue"
	export default {
		data() {
			return {
				name: "",
				username: "",
				Invitationc: "",
				phone: "",
				password: "",
				vercode: "",
				align:""
			}
		},
		onLoad() {

		},
		methods: {
			gologin: function() {
				// uni.switchTab({
				// 	url: '/pages/home/index'
				// })
				uni.request({
					url: 'http://139.159.158.208/api/v1/registers',
					data: {
						name: this.name,
						username: this.username,
						Invitationc: this.Invitationc,
						phone: this.phone,
						password: this.password,
						vercode: this.vercode
					},
					header: {
						'content-type': 'application/x-www-form-urlencoded',
					},
					method: "POST",
					sslVerify: false,
					success: (res) => { 
						console.log(this.align=res.data.code);
						if(res.data.code==401){
							this.align=res.data.errors[0]
							this.$refs.popup.open()
						}else if(res.data.code==10001){
							this.$refs.popup.open()
							this.align=res.data.message
						}else if(res.data.code==200){
							this.$refs.popup.open()
							this.align="注册成功！请登录"
							uni.switchTab({
								url: '/pages/login/index'
							})
						}
					},
				});

			}
		},
		components: {uniPopup}
	}
</script>

<style>
	.place {
		color: #FFFFFF;
	}

	.popup_style{
		color: #FFFFFF;
		font-size: 20px;
	}

	.correct {
		width: 90%;
		height: 1px;
		background: #199ED8;
	}

	.mistake {
		width: 90%;
		height: 1px;
		background: #ff0000;
	}

	page {
		background: #2487ED;
	}

	.register {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.register .register_tab {
		width: 90%;
		height: 50px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.register .register_tab .register_title {
		width: 40%;
		height: 50px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	
	.register .register_tab .register_title image{
		width: 100%;
		height: 80%;
	}

	.register .register_tab .register_account {
		height: 50px;
		width: 100%;
		font-size: 14px;
		color: #FFFFFF;
		/* background: #FFFFFF; */
	}
	.register .register_tab .register_account_1 {
		height: 50px;
		width: 60%;
		font-size: 14px;
		color: #FFFFFF;
		/* background: #FFFFFF; */
	}
	.register .register_button {
		width: 80%;
		margin-top: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
		border-radius: 20rpx;
		height: 40px;
		background: #dee5fa;
		color: #2487ED;
		font-weight: 600;
	}
</style>
