<template>
	<view class="content">
		<view class="zhscicon icon-lanmu" @click="openPerson()"></view>
		<view class="top">
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
				:duration="duration">
				<swiper-item>
					<view class="topContent">
						<image src="../../static/image/banner.png"></image>
						<view class="tText">
							<view class="title">永觉法师</view>
							<text
								style="font-size: 13px;">号"无觉子",名"朱神光",觉性油画艺术家,中国国内最优秀的油画家之一。其画作中总是充满一种来自大千世界的美，让人感受到画中蕴含的艺术大家风范。</text>
						</view>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="topContent">
						<image src="../../static/image/banner.png"></image>
						<view class="tText">
							<view class="title">永觉法师</view>
							<text
								style="font-size: 13px;">号"无觉子",名"朱神光",觉性油画艺术家,中国国内最优秀的油画家之一。其画作中总是充满一种来自大千世界的美，让人感受到画中蕴含的艺术大家风范。</text>
						</view>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="topContent">
						<image src="../../static/image/banner.png"></image>
						<view class="tText">
							<view class="title">永觉法师</view>
							<text
								style="font-size: 13px;">号"无觉子",名"朱神光",觉性油画艺术家,中国国内最优秀的油画家之一。其画作中总是充满一种来自大千世界的美，让人感受到画中蕴含的艺术大家风范。</text>
						</view>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="menu">
			<view class="m-item" @click="goPage('/pages/list1/list1')">
				<view class="m-img">
					<image src="../../static/image/icon-1.png" mode="widthFix"></image>
				</view>
				<view class="m-text">梵呗经咒</view>
			</view>
			<view class="m-item" @click="goPage('/pages/live/live')">
				<view class="m-img">
					<image src="../../static/image/icon-2.png" mode="widthFix"></image>
				</view>
				<view class="m-text">直播开示</view>
			</view>
			<view class="m-item" @click="goPage('/pages/faqi/faqi')">
				<view class="m-img">
					<image src="../../static/image/icon-3.png" mode="widthFix"></image>
				</view>
				<view class="m-text">法器结缘</view>
			</view>
			<view class="m-item">
				<view class="m-img">
					<image src="../../static/image/icon-4.png" mode="widthFix"></image>
				</view>
				<view class="m-text">佛事祈福</view>
			</view>
		</view>
		<uni-popup ref="personPop" type="left">
			<!-- 名片整个弹框 -->
			<view class="personBox">
				<view class="zhscicon icon-close-blod" @click="personPopClose()"></view>
				<!-- 名片个人信息框 -->
				<view class="personMessage">
					<view class="mess-top" @click="openLogin()">
						<image src="../../static/image/logo.png" mode="widthFix"></image>
						<view class="top-text">请登录</view>
					</view>
					<!-- 功能框 -->
					<view class="sec-box">
						<view class="mess-sec" style="border-bottom: 1px solid #a8594c;">
							<view class="sec-line">
								<image src="../../static/image/dingdan-2.png" mode="widthFix"></image>
								<view class="sec-text">我的订单</view>
							</view>
							<view class="zhscicon icon-arrow-right"></view>
						</view>
						<view class="mess-sec" style="border-bottom: 1px solid #a8594c;">
							<view class="sec-line">
								<image src="../../static/image/dizhi.png" mode="widthFix"></image>
								<view class="sec-text">收货地址</view>
							</view>
							<view class="zhscicon icon-arrow-right"></view>
						</view>
						<view class="mess-sec">
							<view class="sec-line">
								<image src="../../static/image/dingdan-2.png" mode="widthFix"></image>
								<view class="sec-text">联系我们：0772-55555</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</uni-popup>
		<uni-popup ref="loginPop" type="center">
			<view class="loginBox">
				<view class="zhscicon icon-close-blod" @click="loginPopClose()"></view>
				<image src="../../static/image/logo.png" mode="widthFix"></image>
				<view class="loginFirLine">
					<input type="number" placeholder="请输入手机号码">
					<view style="color: #a8594c;">获取验证码</view>
				</view>
				<view class="loginFirLine">
					<input type="number" placeholder="请输入验证码" />
				</view>
				<view class="loginBtn">登录</view>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	var _this;
	import uniPopup from '@/components/uni-popup/uni-popup.vue'
	import uniPopupMessage from '@/components/uni-popup/uni-popup-message.vue'
	import uniPopupDialog from '@/components/uni-popup/uni-popup-dialog.vue'
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		components: {
			uniPopup,
			uniPopupMessage,
			uniPopupDialog
		},
		onLoad() {

		},
		methods: {
			changeIndicatorDots(e) {
				this.indicatorDots = !this.indicatorDots
			},
			changeAutoplay(e) {
				this.autoplay = !this.autoplay
			},
			intervalChange(e) {
				this.interval = e.target.value
			},
			durationChange(e) {
				this.duration = e.target.value
			},
			openPerson() {
				this.$refs.personPop.open()
			},
			openLogin() {
				this.$refs.loginPop.open()
			},
			loginPopClose() {
				this.$refs.loginPop.close()
			},
			personPopClose(){
				this.$refs.personPop.close()
			},
			goPage(url) {
				uni.navigateTo({
					url: url
				});
			},

		}
	}
</script>

<style lang="scss">
	page {
		background-color: #3c3233;
	}

	.content {
		display: flex;
		flex-direction: column;
	}

	.icon-lanmu {
		position: absolute;
		top: 50rpx;
		left: 25rpx;
		color: #FFFFFF;
		z-index: 10;
		font-size: 15px;
		font-weight: bold;
	}

	.swiper {
		height: 70vh !important;
		width: 100vw !important;
		// display: none;

	}

	/deep/.uni-scroll-view ::-webkit-scrollbar {
		display: none;
		width: 0;
		height: 0;
		color: transparent;
		background: transparent;
	}

	/deep/.uni-swiper-dot-active {
		background-color: #FFFFFF;
	}


	.topContent,
		{
		image {
			height: 70vh;
			width: 100vw;
		}

		.tText {
			position: relative;
			left: 50rpx;
			bottom: 320rpx;
			width: 500rpx;
			color: #FFFFFF;
            overflow: hidden;
			text-overflow: ellipsis;
			.title {
				font-size: 21px;
				font-weight: bold;
				letter-spacing: 6rpx;
				margin-bottom: 20rpx;
			}

		}
	}

	.menu {
		display: flex;
		justify-content: space-around;
		height: 23vh;
		margin: 0 50rpx;
		align-items: center;

		.m-item {
			align-items: center;

			.m-img {
				background-color: #FFFFFF;
				width: 120rpx;
				height: 120rpx;
				border-radius: 60rpx;
				align-items: center;
				display: flex;
				justify-content: center;

				image {
					width: 100rpx;
				}
			}

			.m-text {
				color: #FFFFFF;
				margin-top: 20rpx;
				font-size: 15px;
			}
		}
	}


	.uni-popup__wrapper-box {
		width: 60vw !important;
	}

	.personBox {
		height: 100vh;
		width:60vw;
		background-color: #FFFFFF;
         .icon-close-blod {
         	font-size: 15px;
         	color: #a8594c;
         	position: absolute;
         	top: 20rpx;
         	left: 55vw;
         }
		.personMessage {
			padding: 80rpx 40rpx 0 40rpx;

			.mess-top {
				display: flex;
				align-items: center;

				image {
					width: 120rpx;
				}

				.top-text {
					margin-left: 10rpx;
					letter-spacing: 2rpx;
				}
			}

			.sec-box {
				margin-top: 150rpx;

			}

			.mess-sec {
				display: flex;
				justify-content: space-between;
				align-items: center;
				// border-bottom: 1px solid #aa6154;
				padding-bottom: 20rpx;
				margin-top: 40rpx;

				.sec-line {
					display: flex;
					align-items: center;

					image {
						width: 40rpx;
					}

					.sec-text {
						margin-left: 20rpx;
						font-size: 13px;
					}
				}
			}
		}
	}



	.loginBox {
		width: 60vw;
		height: 500rpx;
		padding: 0 80rpx 0 80rpx;
		background-color: #FFFFFF;
		display: flex;
		flex-direction: column;
		justify-content: center;
		border-radius: 20rpx;
		align-items: center;

		image {
			width: 110rpx;
			margin-bottom: 50rpx;
		}

		.icon-close-blod {
			font-size: 15px;
			color: #a8594c;
			position: absolute;
			top: 20rpx;
			left: 20rpx;
		}

		.loginFirLine {
			display: flex;
			justify-content: space-between;
			border-bottom: 1px solid #a8594c;
			padding-bottom: 20rpx;
			width: 60vw;
			white-space: nowrap;
			margin-bottom: 30rpx;
			font-size: 13px;

			input {
				font-size: 13px;
			}
		}

		.loginBtn {
			width: 100rpx;
			background-color: #a8594c;
			border-radius: 10rpx;
			color: #FFFFFF;
			text-align: center;
			padding: 10rpx 20rpx 10rpx 20rpx;
			margin-top: 20rpx;
			letter-spacing: 4rpx;
			font-size: 14px;
		}
	}
</style>
