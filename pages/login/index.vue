<template>
	<view class="login">
		<view class="login_logo">
			<view class="login_logo_img">
				<image src="../../static/imgs/heda_cs.jpg" mode=""></image>
			</view>
		</view>
		<view class="login_tab">
			<view class="login_title">
				账号
			</view>
			<input type="confirmtype" value="" placeholder="请输入您要登陆的账号" class="login_account" v-model="name" placeholder-class="place"/>
			
		</view>
		<view class="login_border"></view>
		<view class="login_tab">
			<view class="login_title">
				密码
			</view>
			<input type="confirmtype" value="" placeholder="请输入您要登陆的密码" class="login_account" v-model="password" placeholder-class="place"/>
		</view>
		<view class="login_border"></view>
		<view class="login_tab">
			<view class="login_title_go">
				验证码
			</view>
			<input type="confirmtype" value="" placeholder="请输入验证码" class="login_verify" v-model="vercode" placeholder-class="place"/>
			<view class="login_verify_img">
				<image src="http://139.159.158.208/api/v1/captcha" mode=""></image>
			</view>
		</view>
		<view class="login_border" v-show="iflase"></view>
		<view class="login_border_1" v-show="iftrue"></view>
		<view class="login_aleat">
			<text class="login_aleat_1" v-show="ifaleat">你的账号或密码错误请检查</text>
			<text class="login_aleat_1" v-show="ifaleat_1">验证码错误</text>
			<text class="login_aleat_1" v-show="ifaleat_2">未知的错误</text>
		</view>
		<view class="login_register" @click="goregister">
			没有账号，请注册
		</view>
		<view class="login_button" @click="gohome">
			登陆
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name:"",
				password:"",
				vercode:"",
				iftrue:false,
				ifaleat:false,
				ifaleat_1:false,
				ifaleat_2:false,
				iflase:true
			}
		},
		onLoad() {
				
		},
		methods: {
			gohome:function(){
					// if(this.name==""){
					// 	console.log(1)
					// }
					uni.request({
					    url: 'http://139.159.158.208/api/v1/index',
						data: {
						   name:this.name,
						   password:this.password,
						   vercode:this.vercode
						},
						header: {
							'content-type': 'application/x-www-form-urlencoded', 
						},
						method:"POST",
						sslVerify:false,
					    success: (res) => {
					        console.log(res.data);
							if(res.data.code==401){
								this.iflase=false
								this.iftrue=true
								this.ifaleat_1=true
							}else if(res.data.code==10002){
								this.iflase=false
								this.iftrue=true
								this.ifaleat=true
							}else if(res.data.code==30001){
								this.iflase=false
								this.iftrue=true
								this.ifaleat_2=true
							}else if(res.data.code==200){
								uni.switchTab({
									url: '/pages/home/index'
								})
							}
							
					    },
					}); 
			},
			goregister:function(){
				uni.navigateTo({
					url: '/pages/login/register/index',
				})
			}
		}
	}
</script>

<style>
	.place{
		color: #FFFFFF;
	}
	.login_register{
		height: 40px;
		color: #FFFFFF;
		display: flex;
		align-items: center;
	}
	.login_aleat_1{
		height: 20px;
		color: #FF0000;
	}
	.login_border{
		height: 1px;
		width: 90%;
		background: #199ED8;
	}
	.login_border_1{
		height: 1px;
		width: 90%;
		background: #FF0000;
	}
	page{
		background: #2487ED;
	}
	.login {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.login .login_logo{
		width: 100%;
		height: 200px;
		background: #2487ED;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.login .login_logo .login_logo_img{
		height: 100px;
		width: 100px;
		background: #4CD964;
	}
	.login .login_logo .login_logo_img image{
		width: 100%;
		height: 100%;
	}
	.login .login_tab{
		width: 90%;
		height: 50px;
		/* background: #199ED8; */
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.login .login_tab .login_title{
		color: #FFFFFF;
		width: 25%;
		font-size: 16px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.login .login_tab .login_title_go{
		color: #FFFFFF;
		width: 25%;
		font-size: 16px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.login .login_tab .login_account{
		height: 50px;
		width: 75%;
		font-size: 14px;
		color: #FFFFFF;
		/* background: #FFFFFF; */
	}
	.login .login_tab .login_verify{
		height: 50px;
		width: 40%;
		font-size: 14px;
		color: #FFFFFF;
		/* background: #FFFFFF; */
	}
	.login .login_tab .login_verify_img{
		height: 40px;
		width: 40%;
	}
	.login .login_tab .login_verify_img image{
		width: 100%;
		height: 100%;
	}
	.login .login_button{
		width: 80%;
		margin-top: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 14px;
		border-radius:20rpx ;
		height: 40px;
		background: #dee5fa;
		color: #2487ED;
		font-weight: 600;
	}
</style>
