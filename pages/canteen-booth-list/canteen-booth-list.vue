<template>
  <view class="flex-col page">
    <view class="flex-col section_2">
      <view class="flex-col list space-y-8" v-for="(booth, i) in boothList" :key="i">
        <view class="flex-row items-center list-item space-x-12" @click="gotoBoothDetail(booth.booth_id)">
          <image
            class="shrink-0 image_3"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218751562843398.png"
          />
          <view class="flex-col flex-auto space-y-6">
            <text class="self-start font_1 text_2">{{booth.booth_name}} 排队约{{booth.avg_number}}人</text>
            <text class="font_2">
              提供美味的中餐，有丰富的菜品选择，供应新鲜健康的食材，受到学生们的喜爱。
            </text>
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
        boothList: [],
      };
    },
	
		onLoad(options) {
			this.getBoothList(options)
		},

    methods: {
		async getBoothList(options) {
			const {
				data: res
			} = await uni.$http.get('/traffic/canteens/' + options.canteen_id)
			if (res.code !== 200) return uni.$showMsg()
			this.boothList = res.data
		},
		
		gotoBoothDetail(booth_id) {
			uni.navigateTo({
				url: "/pages/canteen-booth-detail/canteen-booth-detail?booth_id=" + booth_id
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
    .section {
      padding: 38.46rpx 51.92rpx 26.92rpx 73.08rpx;
      background-color: #ffffff;
      .image {
        width: 61.54rpx;
        height: 25rpx;
      }
      .image_2 {
        width: 148.08rpx;
        height: 25rpx;
      }
    }
    .section_2 {
      background-color: #ffffff;
      .text-wrapper {
        padding: 30.77rpx 0 19.23rpx;
        background-color: #ffffff;
        .text {
          margin-left: 30.77rpx;
        }
      }
      .list {
        padding: 0 30.77rpx 11.54rpx;
        .list-item {
          padding: 23.08rpx 23.08rpx 15.38rpx;
          background-color: #f7f8fa;
          border-radius: 23.08rpx;
          .image_3 {
            border-radius: 23.08rpx;
            width: 123.08rpx;
            height: 123.08rpx;
          }
          .space-y-6 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 11.54rpx;
            }
            .text_2 {
              line-height: 27.88rpx;
            }
          }
        }
      }
    }
    .section_3 {
      padding-top: 15.38rpx;
      background-color: #ffffff;
      backdrop-filter: blur(38.46rpx);
      .section_4 {
        padding: 26.92rpx 30.77rpx 19.23rpx;
        background-color: #ffffff;
        .group {
          margin-right: 3.85rpx;
          .text_3 {
            line-height: 25rpx;
          }
          .image_4 {
            width: 15.38rpx;
            height: 23.08rpx;
          }
        }
      }
      .waterfall {
        margin: 0 30.77rpx;
        .group_3 {
          flex: 1 1 332.69rpx;
        }
        .group_4 {
          flex: 1 1 332.69rpx;
          .group_6 {
            border-radius: 23.08rpx;
            overflow: hidden;
          }
        }
        .waterfall-item {
          padding-bottom: 15.38rpx;
          background-color: #f7f8fa;
          border-radius: 23.08rpx;
          overflow: hidden;
          .section_5 {
            padding: 15.38rpx 0 376.92rpx;
            border-radius: 23.08rpx 23.08rpx 0px 0px;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218752374975963.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
          .section_6 {
            padding: 15.38rpx 0 230.77rpx;
            border-radius: 23.08rpx 23.08rpx 0px 0px;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218752835519176.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
        }
        .space-y-9 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 17.31rpx;
          }
        }
        .section_7 {
          margin-right: 15.38rpx;
          padding: 9.62rpx 15.38rpx;
          background-color: #00000033;
          border-radius: 1921.15rpx;
          backdrop-filter: blur(19.23rpx);
          .image_5 {
            width: 25rpx;
            height: 26.92rpx;
          }
          .font_3 {
            font-size: 23.08rpx;
            font-family: MiSans;
            line-height: 18.27rpx;
            color: #ffffff;
          }
        }
        .font_4 {
          font-size: 26.92rpx;
          font-family: MiSans;
          line-height: 25rpx;
          color: #1d2129;
        }
        .text_4 {
          margin-left: 23.08rpx;
        }
        .group_5 {
          padding: 0 23.08rpx;
          .font_6 {
            font-size: 23.08rpx;
            font-family: MiSans;
            line-height: 21.15rpx;
            color: #86909c;
          }
        }
        .section_8 {
          margin-top: 30.77rpx;
          .section_10 {
            padding: 15.38rpx 0 230.77rpx;
            border-radius: 23.08rpx 23.08rpx 0px 0px;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218752584442309.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
          .section_9 {
            padding: 15.38rpx 0 376.92rpx;
            border-radius: 23.08rpx 23.08rpx 0px 0px;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218753574091692.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
          .section_11 {
            padding: 15.38rpx 23.08rpx;
            background-color: #f7f8fa;
          }
        }
        .space-x-6 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 11.54rpx;
          }
        }
        .image_6 {
          border-radius: 2190.38rpx;
          width: 30.77rpx;
          height: 30.77rpx;
        }
        .font_5 {
          font-size: 23.08rpx;
          font-family: MiSans;
          line-height: 18.27rpx;
          color: #86909c;
        }
      }
      .group_2 {
        padding: 15.38rpx 0;
      }
      .space-x-4 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 7.69rpx;
        }
      }
    }
    .font_1 {
      font-size: 30.77rpx;
      font-family: MiSans;
      line-height: 28.85rpx;
      color: #1d2129;
    }
    .font_2 {
      font-size: 26.92rpx;
      font-family: MiSans;
      line-height: 42.31rpx;
      color: #86909c;
    }
    .space-x-12 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 23.08rpx;
      }
    }
    .space-y-8 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 15.38rpx;
      }
    }
    .section_12 {
      padding: 30.77rpx 61.54rpx;
      background-color: #ffffff;
      backdrop-filter: blur(19.23rpx);
      border-top: solid 1.92rpx #e5e6eb;
      .text-wrapper_2 {
        width: 125rpx;
        .font_7 {
          font-size: 30.77rpx;
          font-family: MiSans;
          line-height: 28.85rpx;
          color: #86909c;
        }
      }
      .text_5 {
        color: #ffb900;
      }
    }
  }
</style>