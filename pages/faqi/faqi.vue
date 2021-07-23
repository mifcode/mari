<template>
	<view>
		<view class="firstLine">
			<view class="zhscicon icon-lanmu" @click="openPerson()"></view>
			<view class="f-right" @click="buyCar()">
				<view class="zhscicon icon-gouwuchekong"></view>
				<view class="carText">x 3</view>
			</view>
		</view>
		<view class="buyCarbox">
			<view class="buyPic">
				<image src="../../static/image/2.png" mode="widthFix"></image>
			</view>
			<view class="shangpin">
				<view class="s-name">商品名称</view>
				<view class="s-price">4,800元</view>
			</view>
			<view class="tianjia" @click="buy=1">
				<image src="../../static/image/jia.png" mode="widthFix" v-if="buy!=1"></image>
				<image src="../../static/image/gou.png" mode="widthFix" v-if="buy==1"></image>
			</view>
		</view>
		<view class="buyCarbox">
			<view class="buyPic">
				<image src="../../static/image/2.png" mode="widthFix"></image>
			</view>
			<view class="shangpin">
				<view class="s-name">商品名称</view>
				<view class="s-price">4,800元</view>
			</view>
			<view class="tianjia" @click="buy=1">
				<image src="../../static/image/jia.png" mode="widthFix" v-if="buy!=1"></image>
				<image src="../../static/image/gou.png" mode="widthFix" v-if="buy==1"></image>
			</view>
		</view>
		<view class="buyCarbox">
			<view class="buyPic">
				<image src="../../static/image/2.png" mode="widthFix"></image>
			</view>
			<view class="shangpin">
				<view class="s-name">商品名称</view>
				<view class="s-price">4,800元</view>
			</view>
			<view class="tianjia" @click="buy=1">
				<image src="../../static/image/jia.png" mode="widthFix" v-if="buy!=1"></image>
				<image src="../../static/image/gou.png" mode="widthFix" v-if="buy==1"></image>
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
		<uni-popup ref="buyCarPop" type="bottom">
			<view class="buyCarContent">
				<view class="goodsDetail">
					<view class="goodsPic">
						<image src="../../static/image/1.png" mode="widthFix"></image>
					</view>
					<view class="s-name">商品名称 x 1</view>
					<view class="s-price">4,800元</view>
				</view>
				<view class="goodsDetail">
					<view class="goodsPic">
						<image src="../../static/image/1.png" mode="widthFix"></image>
					</view>
					<view class="s-name">商品名称 x 1</view>
					<view class="s-price">4,800元</view>
				</view>
				<view class="total">
					<view class="total-text">总金额</view>
					<view class="total-price">= 14000元</view>
				</view>
				<view class="pay">支付</view>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				buy: undefined,
			}
		},
		methods: {
			openPerson() {
				this.$refs.personPop.open()
			},
			personPopClose() {
				this.$refs.personPop.close()
			},
			buyCar() {
				this.$refs.buyCarPop.open()
			}
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

		.f-right {
			display: flex;
			color: #FFFFFF;
			align-items: center;

			.icon-gouwuchekong {
				color: #FFFFFF;
				z-index: 10;
				font-size: 22px;
				margin-right: 10rpx;
			}

			.carText {
				font-size: 20px;
			}
		}
	}

	.buyCarbox {
		background-color: #a8594c;
		width: 80vw;
		height: 40vw;
		margin-left: 20vw;
		margin-top: 15vw;
		border-radius: 40rpx;
		position: relative;

		.buyPic {
			position: relative;

			image {
				width: 100%;
				width: 32vw;
				position: absolute;
				top: -60rpx;
				left: 10vw;
			}
		}

		.shangpin {
			position: absolute;
			bottom: 7vw;
			right: 10vw;

			.s-name {
				color: #FFFFFF;
				margin-bottom: 6rpx;
				font-size: 15px;
			}

			.s-price {
				color: #d09182;
			}
		}

		.tianjia {
			background-color: #FFFFFF;
			width: 90rpx;
			height: 90rpx;
			border-radius: 45rpx;
			display: flex;
			justify-content: center;
			align-items: center;
			position: absolute;
			bottom: -50rpx;
			right: 12vw;

			image {
				width: 50rpx;
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

	.buyCarContent {
        text-align: center;
		background-color: #a8594c;
		border-top-left-radius: 40rpx;
		border-top-right-radius: 40rpx;
		padding-top: 80rpx;
		padding-bottom: 120rpx;
		align-items: center;
		justify-content: center;
        .goodsDetail{
			display: flex;
			justify-content: space-around;
			margin-top: 60rpx;
			align-items: center;
		}
		.goodsPic {
			background-color: #FFFFFF;
			width: 150rpx;
			height: 150rpx;
			border-radius: 75rpx;
			display: flex;
			justify-content: center;
			align-items: center;

			image {
				width: 90rpx;
			}
		}

		.s-name {
			color: #FFFFFF;
			margin-bottom: 6rpx;
			font-size: 15px;
		}

		.s-price {
			color: #d09182;
		}
		.total{
			display: flex;
			color: #FFFFFF;
			margin: 50rpx 60rpx 0 60rpx;
			border-top: 1px solid #d09182;
			text-align: center;
			justify-content: space-around;
			padding-top: 80rpx;
			.total-text{
				font-size: 18px;
				letter-spacing: 6rpx;
			}
			.total-price{
				font-size: 17px;
				letter-spacing: 6rpx;
			}
		}
		.pay{
			background-color: #FFFFFF;
			text-align: center;
			padding:30rpx 120px ;
			margin: 100rpx 100rpx 0 100rpx;
			border-radius: 80rpx;
			font-size: 20px;
			color: #ac554e;
			font-weight: bold;
		}
	}
</style>
