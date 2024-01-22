<template>
	<view class="flex-col">
		<view class="flex-row top">
			<!-- titleArr: 选择项数组 dropArr: 下拉项数组 二维数组 @finishDropClick: 下拉筛选完成事件-->
			<cc-dropDownMenu :titleArr="titleArr" :dropArr="dropArr" @finishDropClick="setParam"></cc-dropDownMenu>
			<zg-button @click="getTrafficList" type="primary" plain>按钮</zg-button>
		</view>

		<view class="charts-box">
			<qiun-data-charts type="line" :opts="opts" :chartData="chartData" />
		</view>

	</view>

</template>

<script>
	export default {

		data() {
			return {
				chartData: {},
				//您可以通过修改 config-ucharts.js 文件中下标为 ['line'] 的节点来配置全局默认参数，如都是默认参数，此处可以不传 opts 。实际应用过程中 opts 只需传入与全局默认参数中不一致的【某一个属性】即可实现同类型的图表显示不同的样式，达到页面简洁的需求。
				opts: {
					color: ["#1890FF", "#91CB74", "#FAC858", "#EE6666", "#73C0DE", "#3CA272", "#FC8452", "#9A60B4", "#ea7ccc"],
					padding: [15, 10, 0, 15],
					enableScroll: true, // 允许滚动
					legend: {},
					// https://www.ucharts.cn/v2/#/document/index
					xAxis: {
						disableGrid: true,
						rotateLabel: true,
						rotateAngle: 45,
						labelCount: 5,
						scrollShow: true,
						scrollAlign: "right",
						itemCount: 30
					},
					yAxis: {
						gridType: "dash",
						dashLength: 2
					},
					extra: {
						line: {
							type: "curve",
							width: 2,
							activeType: "hollow"
						}
					}
				},
				
				// filter
				titleArr: ['日期', '时间'],
				dropArr: [
					// 日期
					[{
							text: '2023-11-10',
							value: "20231110"
						},
						{
							text: '2023-11-11',
							value: "20231111"
						}
					],
					// 时间
					[{
							text: '早餐',
							value: 0
						}, {
							text: '午餐',
							value: 1
						},
						{
							text: '晚餐',
							value: 2
						}
					]
				],

				// traffic拆开
				timeList: [],
				numberList: [],
				
				// requests get
				params: {
					"date": "20231111",
					"meal": 0
				},
				
				// plot data
				plotData: {}
			}
		},
		onLoad(options) {
			this.options = options
		},


		methods: {
			setParam(filter) {
				this.params["date"] = filter[0] || this.params["date"]
				this.params["meal"] = filter[1] || this.params["meal"]
			},

			async getTrafficList() {
				const {
					data: res
				} = await uni.$http.get('/traffic/booths/' + this.options.booth_id, this.params);
				if (res.code !== 200) return uni.$showMsg();
				const trafficList = res.data;
				trafficList.forEach((item) => {
					this.timeList.push(this.dateFormat(item.time));
					this.numberList.push(item.number);
				});
				
				this.plotData = {
					categories: this.timeList,
					series: [{
						name: "人流量",
						data: this.numberList
					}]
				};
				this.chartData = JSON.parse(JSON.stringify(this.plotData));
			},
			
			dateFormat(dateTimeString) {
				// 提取小时和分钟
				const date = new Date(dateTimeString);
				const hours = date.getHours();
				const minutes = date.getMinutes();
				
				// 格式化小时和分钟
				const formattedTime = `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}`;
				
				return formattedTime;
			}
		}
	}
</script>

<style scoped lang="scss">
	.top {
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>