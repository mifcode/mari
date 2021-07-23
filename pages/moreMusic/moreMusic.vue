<template>
	<view>
		<view class="zhscicon icon-lanmu" @click="openPerson()"></view>
		<view class="topBox">
			<image src="../../static/image/introImg.png" mode="widthFix"></image>
			<view class="boxRight">
				<view class="r-top" v-if="showType==1">
					<view class="topTitle">热门曲目</view>
					<image src="../../static/image/hot.png" mode="widthFix"></image>
				</view>
				<view class="r-top" v-if="showType==2">
					<view class="topTitle">热门曲目</view>
					<image src="../../static/image/recently.png" mode="widthFix"></image>
				</view>
				<view class="topText">永觉法师</view>
				
			</view>
		</view>
		<view class="list-menu">
			<view :class="a===1?'listNameSe':'listName'" >专题目录</view>
			<view :class="a===2?'listNameSe':'listName'" @click="a=2">专题推荐</view>
			<view :class="a===3?'listNameSe':'listName'">我的收藏</view>
		</view>
		<view class="listContent" v-if="a==2">
			<view class="cTop">
				<view class="tLine">
					<view class="zhscicon icon-bofang"></view>
				</view>
				<view class="tText">全部播放(300)</view>
			</view>
			<view class="cName" @click="jiesuo()">
				<view class="nText">1 - 穿越时空之旅</view>
				<view class="zhscicon icon-bofang"></view>
			</view>
			<view class="cName" @click="jiesuo()">
				<view class="nText">1 - 穿越时空之旅</view>
				<view class="zhscicon icon-bofang" ></view>
			</view>
			<view class="cName" @click="jiesuo()">
				<view class="nText">1 - 穿越时空之旅</view>
				<view class="zhscicon icon-bofang"></view>
			</view>
			<view class="cName" @click="jiesuo()">
				<view class="nText">1 - 穿越时空之旅</view>
				
				<view class="zhscicon icon-bofang"></view>
			</view>
		</view>
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
				a: undefined,
				b: undefined,
				c:undefined,
				showType:undefined
			}
		},
		components: {
			uniPopup,
			uniPopupMessage,
			uniPopupDialog
		},
		onLoad(options) {
			_this = this;
			this.showType = options.showType;
			this.a = 2,
			this.b = 1
		},
		methods: {
			changeListName() {
				this.a = value
			},
			jiesuo() {
				this.$refs.jiesuoPop.open()
			},
			comfirmPay() {
				this.b = 2,
					this.$refs.jiesuoPop.close()
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
		background-color: #2c2223;
		padding: 50rpx 25rpx 25rpx 25rpx;
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

	.topBox {
		background-color: #3c3233;
		padding: 20rpx 20rpx 20rpx 20rpx;
		display: flex;
		margin-top: 70rpx;
		border-radius: 20rpx;

		image {
			width: 260rpx;
		}

		.boxRight {
			display: flex;
			flex-direction: column;
			color: #FFFFFF;
			padding: 30rpx 20rpx 20rpx 40rpx;

			.r-top {
				margin-top: 20rpx;
                display: flex;
				align-items: center;
				.topTitle {
					font-size: 21px;
					font-weight: bold;
					letter-spacing: 4rpx;
				}
				image{
					width: 50rpx;
				}

				.topText {
					font-size: 13px;
					margin-top: 8rpx;
				}
			}

			.r-bottom {
				display: flex;
				font-size: 15px;

				.icon-gouwuchekong {
					font-size: 17px;
					margin-right: 10rpx;
				}
			}
		}
	}

	.list-menu {
		display: flex;
		justify-content: space-between;
		margin-top: 40rpx;

		.listName {
			color: #FFFFFF;
			padding: 20rpx 40rpx 20rpx 40rpx;
			background-color: #3c3233;
			font-size: 15px;
		}

		.listNameSe {
			color: #9c5959;
			padding: 20rpx 40rpx 20rpx 40rpx;
			background-color: #3c3233;
			font-size: 15px;
		}
	}

	.listContent {
		margin-top: 40rpx;
		background-color: #3c3233;
		padding: 40rpx 20rpx 40rpx 20rpx;
		color: #FFFFFF;
		align-items: center;

		.cTop {
			display: flex;
			font-size: 14px;
			align-items: center;

			.tLine {
				background-color: #FFFFFF;
				width: 44rpx;
				height: 44rpx;
				border-radius: 22rpx;
				display: flex;
				justify-content: center;
				margin-right: 20rpx;
				align-items: center;

				.icon-bofang {
					color: #99564d;
					font-size: 18px;
				}
			}
		}

		.cName {
			display: flex;
			justify-content: space-between;
			color: #FFFFFF;
			margin-top: 40rpx;
			font-size: 15px;
			align-items: center;

			// border-bottom: 1px solid #FFFFFF;
			.icon-suo,
			.icon-bofang {
				font-size: 20px;
			}
		}

		.tj-top {
			display: flex;
			justify-content: space-between;
			align-items: center;

			.t-t-hot {
				font-size: 17px;
			}

			.t-t-more {
				font-size: 13px;
			}
		}

		.tj-second {
			display: flex;
			justify-content: space-between;
			margin-top: 20rpx;

			.tj-item {
				display: flex;
				flex-direction: column;

				.tj-i-top {
					width: 150rpx;
					position: relative;

					image {
						width: 100%;
					}

					.icon-bofang {
						font-size: 40px;
						position: absolute;
						top: 40rpx;
						right: 40rpx;
					}
				}

				.tj-name {
					font-size: 14px;
				}
			}
		}

		.tj-new {
			display: flex;
			justify-content: space-between;

			.tj-new-item {
				display: flex;
				margin-top: 20rpx;
				align-items: center;
				.tj-n-top {
					width: 100rpx;
					position: relative;

					image {
						width: 100%;
					}

					.icon-bofang {
						font-size: 30px;
						position: absolute;
						top: 20rpx;
						right: 20rpx;
					}
				}
				.tj-new-text{
					margin-left: 20rpx;
					width: 190rpx;
					word-break: keep-all;
					white-space: nowrap;
					overflow: hidden;
					text-overflow: ellipsis;
					
				}

			}
		}
	}

	.jiesuoBox {
		width: 60vw;
		height: 55vw;
		border-radius: 16rpx;
		display: flex;
		justify-content: center;
		flex-direction: column;
		background-color: #FFFFFF;
		align-items: center;

		.jiesuoName {
			font-size: 20px;
			font-weight: bold;
		}

		.price {
			display: flex;
			font-size: 15px;
			margin-top: 20rpx;
		}

		.comfirmPay {
			width: 45vw;
			height: 50rpx;
			color: #FFFFFF;
			background-color: #a8594c;
			text-align: center;
			border-radius: 50rpx;
			margin-top: 40rpx;
			padding: 6rpx 0 6rpx 0;
		}

		.icon-gouwuchekong {
			position: absolute;
			bottom: 10rpx;
		}
	}
</style>
