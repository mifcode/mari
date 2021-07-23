<template>
	<view>
		<view class="zhscicon icon-lanmu" @click="openPerson()"></view>
		<view class="liveContent">
			<view class="live">
				<view class="pic">
					<image src="../../static/image/zhibo1.png" class="live-img" mode="widthFix"></image>
					<image src="../../static/image/shipin.png" class="zhibo-img" mode="widthFix"></image>
				</view>
				<view class="live-text">
					<view style="font-size:17px ;">直播名称</view>
					<view style="font-size: 13px;">直播简介直播简介</view>
				</view>
			</view>
			<view class="live">
				<view class="pic">
					<image src="../../static/image/zhibo1.png" class="live-img" mode="widthFix"></image>
					<image src="../../static/image/shipin.png" class="zhibo-img" mode="widthFix"></image>
				</view>
				<view class="live-text">
					<view style="font-size:17px ;">直播名称</view>
					<view style="font-size: 13px;">直播简介直播简介</view>
				</view>
			</view>
		</view>
		<view class="liveContent">
			<view class="live">
				<view class="pic">
					<image src="../../static/image/zhibo1.png" class="live-img" mode="widthFix"></image>
					<image src="../../static/image/shipin.png" class="zhibo-img" mode="widthFix"></image>
				</view>
				<view class="live-text">
					<view style="font-size:17px ;">直播名称</view>
					<view style="font-size: 13px;">直播简介直播简介</view>
				</view>
			</view>
			<view class="live">
				<view class="pic">
					<image src="../../static/image/zhibo1.png" class="live-img" mode="widthFix"></image>
					<image src="../../static/image/shipin.png" class="zhibo-img" mode="widthFix"></image>
				</view>
				<view class="live-text">
					<view style="font-size:17px ;">直播名称</view>
					<view style="font-size: 13px;">直播简介直播简介</view>
				</view>
			</view>
		</view>
		<view class="liveContent">
			<view class="live">
				<view class="pic">
					<image src="../../static/image/zhibo1.png" class="live-img" mode="widthFix"></image>
					<image src="../../static/image/shipin.png" class="zhibo-img" mode="widthFix"></image>
				</view>
				<view class="live-text">
					<view style="font-size:17px ;">直播名称</view>
					<view style="font-size: 13px;">直播简介直播简介</view>
				</view>
			</view>
			<view class="live">
				<view class="pic">
					<image src="../../static/image/zhibo1.png" class="live-img" mode="widthFix"></image>
					<image src="../../static/image/shipin.png" class="zhibo-img" mode="widthFix"></image>
				</view>
				<view class="live-text">
					<view style="font-size:17px ;">直播名称</view>
					<view style="font-size: 13px;">直播简介直播简介</view>
				</view>
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
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			openPerson() {
				this.$refs.personPop.open()
			},
			personPopClose(){
				this.$refs.personPop.close()
			},
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #2c2223;
		padding: 50rpx 25rpx 25rpx 25rpx;
	}

	.liveContent {
		display: flex;
		justify-content: space-between;
		padding: 10rpx 10rpx;
		margin-top: 30rpx;
	}

	.icon-lanmu {
		color: #FFFFFF;
		z-index: 10;
		font-size: 15px;
		font-weight: bold;
	}

	.live {
		position: relative;
		background-color: #3c3233;
		width: 42vw;
		height: 55vw;
		border-radius: 10rpx;

		.pic {
			width: 42vw;

			.live-img {
				width: 100%;
				border-top-left-radius: 10rpx;
				border-top-right-radius: 10rpx;
			}

			.zhibo-img {
				width: 120rpx;
				position: absolute;
				top: 12vw;
				left: 13vw;
			}
		}

		.live-text {
			padding: 6rpx 6rpx;
			color: #FFFFFF;
			white-space: nowrap;
			overflow: hidden;
			text-overflow: ellipsis;

		}
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
	
</style>
