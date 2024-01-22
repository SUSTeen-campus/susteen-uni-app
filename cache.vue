<template>
	<view class="page">
		<view class="flex-col list">
			<view class="list-item" v-for="(canteen, i) in canteenList" :key="i">
				<view class="flex-col relative group_3">
					<view class=" section_3 pos_2">
						<view class=" section_4">
							<view class="flex-row group_4">
								<image class="shrink-0 image_2"
									src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218735430012074.png" />
								<view class="flex-col flex-auto self-center group_5 space-y-17">
									<text class="self-start font_1">{{canteen.name}}</text>
									<view class="flex-row items-baseline">
										<text class="font_5 text_6">状态</text>
										<text class="font_8">{{canteen.overcrowd}}</text>

									</view>
								</view>
								<view class="flex-col justify-start items-center shrink-0 self-start text-wrapper"
									@click="gotoBooth(canteen.canteen_id)">
									<text class="font_4">进入</text>
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>

</template>

<script>
	export default {
		components: {},
		props: {},
		data() {
			return {
				canteenList: [],
			};
		},
		onLoad() {
			this.getCanteenList()
		},

		methods: {
			async getCanteenList() {
				const {
					data: res
				} = await uni.$http.get('/traffic/canteen_list')
				if (res.status !== 200) return uni.$showMsg()
				this.canteenList = res.message
			},

			gotoBooth(canteen_id) {
				uni.navigateTo({
					url: "/pages/canteen-booth-list/canteen-booth-list?canteen_id=" + canteen_id
				})
			}
		},
	};
</script>

<style scoped lang="scss">
	@mixin space-y($margin_top) {

		&>view:not(:first-child),
		&>text:not(:first-child),
		&>image:not(:first-child) {
			margin-top: $margin_top;
		}
	}

	.section {
		padding: 26.92rpx 30.77rpx;
		background-color: #ffffff;

		.text {
			color: #151b29;
			font-size: 32.69rpx;
			line-height: 30.77rpx;
		}

		.text_2 {
			color: #151b29;
		}

		.pos {
			position: absolute;
			right: 28.85rpx;
			top: 50%;
			transform: translateY(-50%);
		}
	}

	.list {

		// height: 1161.54rpx;
		.list-item {
			padding: 10.85rpx 0 3.85rpx;
			overflow: hidden;

			// background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218731694818346.png);
			// background-size: 100% 100%;
			// background-repeat: no-repeat;
			.group_3 {
				padding-top: 200rpx;

				.section_5 {
					margin: 0 15.38rpx;
					background-color: #00000033;
					border-radius: 15.38rpx;
					backdrop-filter: blur(9.62rpx);
					overflow: hidden;
					height: 134.62rpx;
				}

				.section_3 {
					padding: 19.23rpx 0;
					background-color: #ffffff;

					.section_4 {
						margin: 0 19.23rpx;
						padding-top: 23.08rpx;
						background-color: #ffffff;
						border-radius: 23.08rpx;
						height: 180.77rpx;
						border: solid 1.92rpx #1d2129;

						.group_4 {
							padding: 0 23.08rpx 28.85rpx;

							// border-bottom: solid 1.92rpx #1d2129;
							.image_2 {
								border-radius: 15.38rpx;
								width: 126.92rpx;
								height: 126.92rpx;
							}

							.group_5 {
								margin-left: 15.38rpx;

								.image_3 {
									margin-left: 3.85rpx;
									width: 103.85rpx;
									height: 26.92rpx;
								}

								.font_6 {
									font-size: 23.08rpx;
									font-family: MiSans;
									line-height: 18.27rpx;
									color: #86909c;
								}


								.font_7 {
									font-size: 26.92rpx;
									font-family: MiSans;
									line-height: 21.15rpx;
									color: #1d2129;
								}

								.text_6 {
									margin-left: 23.08rpx;
								}

								.font_8 {
									font-size: 26.92rpx;
									font-family: MiSans;
									line-height: 25rpx;
									color: #1d2129;
								}

								.text_7 {
									margin-left: 23.08rpx;
								}
							}

							.text-wrapper {
								margin-left: 38.46rpx;
								padding: 15.38rpx 0;
								background-color: #1d2129;
								border-radius: 1921.15rpx;
								width: 107.69rpx;
								height: 57.69rpx;

								.font_4 {
									font-size: 26.92rpx;
									font-family: MiSans;
									line-height: 25rpx;
									color: #ffffff;
								}

							}
						}
					}
				}

				.pos_2 {
					position: absolute;
					left: 0;
					right: 0;
					top: 0;
				}
			}
		}


	}

	.font_1 {
		font-size: 30.77rpx;
		font-family: MiSans;
		line-height: 28.85rpx;
		color: #1d2129;
	}

	.font_3 {
		font-size: 26.92rpx;
		font-family: MiSans;
		line-height: 25rpx;
		color: #86909c;
	}

	.font_5 {
		font-size: 23.08rpx;
		font-family: MiSans;
		line-height: 21.15rpx;
		color: #86909c;
	}

	.space-y-17 {

		@include space-y(17rpx)
	}
</style>