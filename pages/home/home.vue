<template>
	<view class="flex-col page">
		<view class="intro">
			<view class="flex-col text space-y-20">
				<text class="font_30">SUSTEEN食堂服务</text>
				<text class="font_27 text_lower">
					SUSTEEN食堂服务是一个致力于提供健康美食的小程序。我们提供丰富多样的菜谱和健康资讯，帮助您保持健康的生活方式。
				</text>
			</view>
		</view>

		<view class="navigation">
			<view class="grid">
				<view class="flex-col items-center relative grid-item space-y-15" @click="gotoMenu">
					<image class="image"
						src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/8a941d16ddb17747f1cd194e611d879f.png" />
					<text>今日菜谱</text>
				</view>


				<view class="flex-col items-center relative grid-item space-y-15" @click="gotoCanteenGuide">
					<image class="image"
						src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/8b6178153da54a59096f7b8591f4ef0c.png" />
					<text>食堂向导</text>
				</view>

				<view class="flex-col items-center relative grid-item space-y-15" @click="gotoFeedback">
					<image class="image"
						src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/77fb515fe4a7eda808565c802da20fa9.png" />
					<text>反馈建议</text>
				</view>
				<view class="flex-col items-center relative grid-item space-y-15" @click="gotoAboutUs">
					<image class="image"
						src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/13d2c254514b65c24513887f8535d712.png" />
					<text>关于我们</text>
				</view>
			</view>
		</view>

		<view class="flex-col traffic">
			<view class="flex-row justify-between items-center upper">
				<text class="font_30">今日人流量</text>
				<view class="flex-row items-center"> 
					<text class="font">查看全部</text>
					<uni-icons type="right" size="15"></uni-icons>
				</view>
			</view>
			<view class="flex-row lower">
				<view class="grow justify-between content" v-for="(item, i) in items" :key="i">
					<view class="flex-col space-y-30">
						<text class="self-start font_23">{{item}}就餐人数</text>
						<text class="font_30">280</text>
						<view class="flex-col justify-start items-center image-wrapper">
							<image class="image_7"
								src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218715843292059.png" />
						</view>
					</view>
				</view>

			</view>
		</view>
		<canteen-list></canteen-list>
	</view>
</template>

<script>
	export default {
		components: {
			
		},
		props: {},
		data() {
			return {
				items: ["中心餐厅", "十栋餐厅"]
			};
		},

		methods: {
			gotoMenu() {
				uni.navigateTo({
					url: "/pages/caipu/caipu"
				})
			},
			gotoCanteenGuide() {
				uni.navigateTo({
					url: "/pages/canteen-guide/canteen-guide"
				})
			},
			gotoAboutUs() {
				uni.navigateTo({
					url: "/pages/about-us/about-us"
				})
			},
			gotoFeedback() {
				uni.navigateTo({
					url: "/pages/feedback/feedback"
				})
			}
		},
	};
</script>

<style scoped lang="scss">
	.page {
		width: 100%;
		overflow-y: auto;
		overflow-x: hidden;
		height: 100%;
	}

	.intro {
		padding: 11rpx 0;
		background-color: #ffffff;

		.text {
			margin: 0 30rpx;
			padding: 23rpx 30rpx 14rpx;
			background-color: #ffffff;
			border-radius: 23rpx;
			// overflow: hidden;
			// height: 188.46rpx;
			border: solid 2rpx #1d2129;

			.text_lower {
				line-height: 34rpx;
			}
		}
	}

	.navigation {
		padding: 23rpx 0;
		background-color: #ffffff;

		.grid {
			margin: 0 30rpx;
			padding: 10rpx 4rpx;
			background-color: #ffffff;
			border-radius: 23rpx;
			border: solid 2rpx #1d2129;
			display: grid;
			// 5列，每列的宽度都应该占据可用空间的相等部分 fractional unit
			grid-template-columns: repeat(4, 1fr);

			.grid-item {
				padding: 11rpx 0 19rpx;

				.image {
					// border-radius: 1920rpx;
					width: 75rpx;
					height: 75rpx;
				}

				text {
					font-size: 23rpx;
					font-family: MiSans;
					line-height: 21rpx;
					color: #4e5969;
				}
			}
		}

		.space-y-15 {

			&>view:not(:first-child),
			&>text:not(:first-child),
			&>image:not(:first-child) {
				margin-top: 15rpx;
			}
		}
	}

	.traffic {
		padding: 11rpx 0;
		background-color: #ffffff;

		.upper {
			padding: 15rpx 30rpx 10rpx;

			.font {
				font-size: 27rpx;
				font-family: MiSans;
				color: #86909c;
			}
		}

		.lower {
			padding: 20rpx 23rpx 20rpx;

			.content {
				padding: 34.62rpx 23.08rpx 26.92rpx 30.77rpx;
				margin: 0 8rpx;
				border-radius: 23rpx;
				border: solid 2rpx #1d2129;

				.image-wrapper {
					padding-bottom: 15.38rpx;
					background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218715378091942.png');
					background-size: 100% 100%;
					background-repeat: no-repeat;

					.image_7 {
						width: 275rpx;
						height: 96.15rpx;
					}
				}
			}
		}
	}

	.space-y-10 {

		&>view:not(:first-child),
		&>text:not(:first-child),
		&>image:not(:first-child) {
			margin-top: 19.23rpx;
		}
	}


	.space-y-20 {

		&>view:not(:first-child),
		&>text:not(:first-child),
		&>image:not(:first-child) {
			margin-top: 20rpx;
		}
	}

	.font_30 {
		font-size: 30rpx;
		font-family: MiSans;
		line-height: 28rpx;
		color: #1d2129;
	}

	.font_27 {
		font-size: 27rpx;
		font-family: MiSans;
		line-height: 25rpx;
		color: #86909c;
	}

	.font_23 {
		font-size: 23rpx;
		font-family: MiSans;
		line-height: 21rpx;
		color: #86909c;
	}

	.space-x-4 {

		&>view:not(:first-child),
		&>text:not(:first-child),
		&>image:not(:first-child) {
			margin-left: 8rpx;
		}
	}

	.space-y-30 {

		&>view:not(:first-child),
		&>text:not(:first-child),
		&>image:not(:first-child) {
			margin-top: 30.77rpx;
		}
	}
</style>