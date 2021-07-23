<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	@font-face {
		font-family: zhscicon;
		font-weight: normal;
		font-style: normal;
		src: url('~@/static/font/iconfont.ttf');
	}
	
	.zhscicon {
		font-family: "zhscicon" !important;
		font-size: 16px;
		font-style: normal;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}
	
	/* 改变弹窗宽度 */
		.uni-popup__wrapper.uni-custom.center .uni-popup__wrapper-box{
			max-width: 100%!important;
			max-height: 100%!important;
		}
		/* 弹窗宽度 */
		.uni-popup__wrapper.uni-custom .uni-popup__wrapper-box{
			width: 100%;
		}
	// 栏目
	.icon-lanmu:before{
		content: "\e632";
	}
	// 右键
	.icon-arrow-right:before{
		content:"\e600";
	}
	// 叉
	.icon-close-blod:before{
		content: "\e601";
	}
	// 购物车空
	.icon-gouwuchekong:before{
		content: "\e602";
	}
	// 播放
	.icon-bofang::before{
		content: "\e710";
	}
	// 暂停
	.icon-zantingtingzhi::before{
		content: "\e62d";
	}
	// 锁
	.icon-suo::before{
		content: "\e61d";
	}
	// 收藏
	.icon-xinaixin:before{
		content: "\e667";
	}
</style>
