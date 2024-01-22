<template>
	<view class="flex-col canteen-list">
		<view class="flex-row list-item items-center" v-for="(canteen, i) in canteenList" :key="i">
			<image class="left-image"
				src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218735430012074.png" />

			<view class="right flex-row grow justify-between">
				<view class="flex-col right-text justify-between items-start">
					<text class="canteen-name font-31">{{canteen.canteen_name}}</text>
					<text class="font-28">最后更新时间：{{timeFormat(canteen.time)}}</text>
					<view class="flex-row status items-baseline">
						<text class="font-23">状态</text>
						<text class="font-28" :style="{color: statuses[0].color}">
							{{statuses[0].status}}
						</text>
					</view>
				</view>
				<view class="enter-button items-center justify-center" @click="gotoBooth(canteen.canteen_id)">
					<text class="enter">进入</text>
				</view>
			</view>
		</view>
	</view>

</template>

<script>
import { initCustomFormatter } from "vue";
	export default {
		// name: "canteen-list",
		data() {
			return {
				canteenList: [],
				statuses: [
					{
						'status': '空闲',
						'color': '#00e800'
					},
					{
						'status': '一般',
						'color': '#e8dc2e'
					},
					{
						'status': '拥挤',
						'color': '#e84100'
					}
				],
				formatter: new Intl.DateTimeFormat('en', {
				  month: '2-digit',
				  day: '2-digit',
				  hour: '2-digit',
				  minute: '2-digit',
				  hour12: false
				})
			};
		},
		onLoad() {
			this.getCanteenList()
		},

		methods: {
			async getCanteenList() {
				const {
					data: res
				} = await uni.$http.get('/traffic/canteens')
				if (res.code !== 200) return uni.$showMsg()
				this.canteenList = res.data
			},

			gotoBooth(canteen_id) {
				uni.navigateTo({
					url: "/pages/canteen-booth-list/canteen-booth-list?canteen_id=" + canteen_id
				})
			},
			
			timeFormat(time) {
				const date = new Date(time)
				const formattedDate = this.formatter.format(date)
				return formattedDate
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

	@mixin font($font_size, $line_height, $color) {
		font-size: $font_size;
		font-family: MiSans;
		line-height: $line_height;
		color: $color;
	}

	.font-23 {
		@include font(23rpx, 21rpx, #86909c)
	}

	.font-28 {
		@include font(28rpx, 25rpx, #1d2129)
	}

	.font-31 {
		@include font(31rpx, 29rpx, #1d2129)
	}

	.canteen-list {
		.list-item {
			margin: 10rpx 20rpx;
			background-color: #ffffff;
			border-radius: 20rpx;
			height: 180rpx;
			border: solid 2rpx #1d2129;

			.left-image {
				margin-left: 20rpx;
				border-radius: 20rpx;
				width: 140rpx;
				height: 140rpx;
			}

			.right {
				height: 120rpx;
				// height: 50%;
				margin: 0rpx 20rpx;

				.right-text {
					.canteen-name {}
				}

				.enter-button {

					background-color: #1d2129;
					border-radius: 20rpx;
					width: 100rpx;
					height: 60rpx;
					display: flex;

					.enter {
						@include font(27rpx, 0rpx, #ffffff)
					}
				}
			}

		}
	}
</style>