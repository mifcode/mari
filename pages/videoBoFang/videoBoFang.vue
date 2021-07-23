<template>
	<view>
		<view class="firstLine">
			<view class="zhscicon icon-lanmu" @click="openPerson()"></view>
			<view class="zhscicon icon-xinaixin"></view>
		</view>
		<view class="videoBox">
			<view class="video-pic">
				<image src="../../static/image/bf-pic.png" mode="widthFix"></image>
			</view>
			<view class="write">{{current.author}}</view>
			<view class="musicName">{{current.name}}</view>
			<view class="audio-controller">
				<view class="zhscicon icon-bofang" @click="pause()"></view>
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
				buy: undefined,
				current: {
					poster: 'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/7fbf26a0-4f4a-11eb-b680-7980c8a877b8.png',
					name: '致爱丽丝',
					author: '暂无',
					src: 'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-hello-uniapp/2cc220e0-c27a-11ea-9dfb-6da8e309e0d8.mp3',
				},
			}
		},
		methods: {
			openPerson() {
				this.$refs.personPop.open()
			},
			personPopClose() {
				this.$refs.personPop.close()
			},
			pause() {
				if (innerAudioContext.paused) {
					innerAudioContext.play();
				} else {
					innerAudioContext.pause();
				}
			},
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #2c2223;
		padding: 50rpx 25rpx 25rpx 25rpx;
	}

	.firstLine {
		display: flex;
		justify-content: space-between;
		align-items: center;

		.icon-lanmu {
			color: #FFFFFF;
			z-index: 10;
			font-size: 15px;
			font-weight: bold;
		}

		.icon-xinaixin {
			color: #FFFFFF;
			z-index: 10;
			font-size: 22px;
			margin-right: 10rpx;
		}

	}

	.videoBox {
		width: 100vw;
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items: center;

		.video-pic {
			margin-top: 80rpx;
			width: 500rpx;
			height: 500rpx;
			border-radius: 250rpx;
			border: 4px solid #423839;
			align-items: center;
			display: flex;
			justify-content: center;

			image {
				width: 480rpx;
				height: 480rpx;
				border-radius: 240rpx;
			}
		}

		.write {
			font-size: 16px;
			color: #676161;
			margin-top: 50rpx;
		}

		.musicName {
			color: #FFFFFF;
			font-size: 19px;
			margin-top: 10rpx;
		}

		.audio-controller {
			background-color: #FFFFFF;
			width: 160rpx;
			height: 160rpx;
			border-radius: 80rpx;
			margin-top: 40rpx;
			display: flex;
			justify-content: center;
			align-items: center;

			.icon-bofang {
				font-size: 20px;
				color: #945a4e;
			}
		}
	}



	.personBox {
		height: 100vh;
		width: 60vw;
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
