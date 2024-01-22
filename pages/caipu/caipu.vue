<template>
  <view class="flex-col page">
    <view class="flex-col section_2">
      <view class="flex-row justify-between items-center section_3">
        <text class="font_1">今日菜单</text>
        <view class="flex-row group space-x-4">
          <text class="font_2">查看全部</text>
          <image
            class="shrink-0 image_3"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218713853375357.png"
          />
        </view>
      </view>
      <view class="flex-col list space-y-8">
        <view class="flex-row items-end list-item space-x-20" v-for="(item, index) in items" :key="index">
          <view class="flex-row flex-auto">
            <image
              class="shrink-0 image_4"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218786431449722.png"
            />
            <view class="flex-col flex-auto group_2 space-y-32">
              <view class="flex-col items-start space-y-10">
                <text class="font_3">红烧肉</text>
                <text class="font_4 text">猪肉香糯可口，回味无穷</text>
              </view>
              <view class="flex-row space-x-2">
                <text class="font_5 text_2">¥</text>
                <text class="font_5">198</text>
              </view>
            </view>
          </view>
        </view>
      </view>
    </view>
    <view class="flex-col section_4">
      <view class="flex-row justify-between items-center section_5">
        <text class="font_1">热门菜品</text>
        <view class="flex-row group_4 space-x-4">
          <text class="font_2">查看全部</text>
          <image
            class="shrink-0 image_3"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218713853375357.png"
          />
        </view>
      </view>
      <view class="flex-row waterfall group_5 space-x-12">
        <view class="flex-col group_6">
          <view class="flex-col waterfall-item space-y-94">
            <view class="flex-row justify-evenly items-center self-end section_6">
              <image
                class="image_6"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218740233968457.png"
              />
              <text class="font_7">129</text>
            </view>
            <view class="flex-col items-start space-y-8">
              <text class="font_8">糖醋排骨</text>
              <text class="font_9 text_7">糖醋排骨是一道经典的中式菜肴，口感酸甜可口，肉质鲜嫩多汁。</text>
            </view>
          </view>
          <view class="flex-col waterfall-item_3 section_8 space-y-180">
            <view class="flex-row justify-evenly items-center self-end section_7">
              <image
                class="image_6"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218740233968457.png"
              />
              <text class="font_7">370</text>
            </view>
            <view class="flex-col items-start space-y-8">
              <text class="font_8">宫保鸡丁</text>
              <text class="font_9 text_7">宫保鸡丁是一道传统的川菜，以鸡肉丁和花生米为主要食材，口味麻辣香浓。</text>
            </view>
          </view>
        </view>
        <view class="flex-col group_7">
          <view class="flex-col waterfall-item_2 space-y-180">
            <view class="flex-row justify-evenly items-center self-end section_7">
              <image
                class="image_6"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218740233968457.png"
              />
              <text class="font_7">202</text>
            </view>
            <view class="flex-col items-start space-y-8">
              <text class="font_8">麻婆豆腐</text>
              <text class="font_9 text_7">麻婆豆腐是一道四川传统名菜，豆腐细嫩，麻辣味浓郁，口感丰富。</text>
            </view>
          </view>
          <view class="flex-col waterfall-item_3 section_9 space-y-94">
            <view class="flex-row justify-evenly items-center self-end section_7">
              <image
                class="image_6"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218740233968457.png"
              />
              <text class="font_7">642</text>
            </view>
            <view class="flex-col items-start space-y-8">
              <text class="font_8">红烧肉</text>
              <text class="font_4 text_7 text_8">红烧肉是中国传统名菜，制作精细，色香味俱佳，肥而不腻，酱香浓郁。</text>
            </view>
          </view>
        </view>
      </view>
    </view>
    <view class="flex-col section_10">
      <view class="flex-row justify-between items-center section_11">
        <text class="font_1">搭配推荐</text>
        <view class="flex-row group_8 space-x-4">
          <text class="font_2">查看全部</text>
          <image
            class="shrink-0 image_3"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218713853375357.png"
          />
        </view>
      </view>
      <view class="flex-row horiz-list">
        <view class="flex-col justify-start horiz-list-item section_12">
          <view class="flex-row section_14 space-x-8">
            <image
              class="shrink-0 self-start image_7"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218790689079807.png"
            />
            <view class="flex-col flex-auto self-center group_9 space-y-2">
              <text class="self-start font_10 text_9">清炒秋葵</text>
              <text class="font_10 text_7 text_10">秋葵富含纤维和维生素，是一道营养丰富的菜肴。</text>
            </view>
          </view>
        </view>
        <view class="flex-col justify-start horiz-list-item_2 section_13">
          <view class="flex-row items-center section_15 space-x-8">
            <image
              class="shrink-0 image_7"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218790689079807.png"
            />
            <view class="flex-col items-start flex-auto space-y-4">
              <text class="font_10">***炒饭</text>
              <text class="font_10 text_7">扬州炒饭是一道经典的中式炒饭，香气四溢，口感丰富。</text>
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
        items: [null, null, null],
        items_1: [null, null],
      };
    },

    methods: {},
  };
</script>

<style scoped lang="scss">
  .page {
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 38.46rpx 51.92rpx 400rpx 73.08rpx;
      backdrop-filter: blur(69.23rpx);
      background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218783608143692.png');
      background-size: 100% 100%;
      background-repeat: no-repeat;
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
      padding: 11.54rpx 30.77rpx 0;
      background-color: #ffffff;
      .section_3 {
        padding: 19.23rpx 0;
        background-color: #ffffff;
        .group {
          margin-right: 7.69rpx;
        }
      }
      .list {
        padding: 19.23rpx 0 11.54rpx;
        .list-item {
          padding: 15.38rpx;
          background-color: #f7f8fa;
          border-radius: 23.08rpx;
          .image_4 {
            border-radius: 23.08rpx;
            width: 169.23rpx;
            height: 169.23rpx;
          }
          .group_2 {
            margin: 3.85rpx 0 7.69rpx 23.08rpx;
            .space-y-10 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 19.23rpx;
              }
              .font_3 {
                font-size: 26.92rpx;
                font-family: MiSans;
                line-height: 25rpx;
                color: #1d2129;
              }
              .text {
                line-height: 23.08rpx;
              }
            }
            .space-x-2 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-left: 3.85rpx;
              }
              .font_5 {
                font-size: 30.77rpx;
                font-family: MiSans;
                line-height: 25rpx;
                color: #009688;
              }
              .text_2 {
                line-height: 24.04rpx;
              }
            }
          }
          .space-y-32 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 61.54rpx;
            }
          }
          .group_3 {
            margin-right: 7.69rpx;
            .image_5 {
              border-radius: 7.69rpx;
              width: 38.46rpx;
              height: 38.46rpx;
            }
          }
          .space-x-16 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 30.77rpx;
            }
            .font_6 {
              font-size: 26.92rpx;
              font-family: MiSans;
              line-height: 21.15rpx;
              color: #1d2129;
            }
            .text_3 {
              line-height: 20.19rpx;
            }
          }
        }
        .space-x-20 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 38.46rpx;
          }
        }
      }
    }
    .section_4 {
      padding-top: 15.38rpx;
      background-color: #ffffff;
      backdrop-filter: blur(38.46rpx);
      .section_5 {
        padding: 26.92rpx 34.62rpx 19.23rpx;
        background-color: #ffffff;
        .group_4 {
          margin-right: 3.85rpx;
        }
      }
      .waterfall {
        margin: 0 30.77rpx;
        .group_6 {
          flex: 1 1 332.69rpx;
          .waterfall-item {
            padding: 15.38rpx 7.69rpx 26.92rpx 23.08rpx;
            border-radius: 23.08rpx;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218788563333122.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
            .section_6 {
              margin-right: 7.69rpx;
              padding: 9.62rpx 15.38rpx;
              background-color: #00000033;
              border-radius: 1921.15rpx;
              backdrop-filter: blur(19.23rpx);
              width: 103.85rpx;
            }
          }
          .section_8 {
            padding: 15.38rpx 7.69rpx 26.92rpx 23.08rpx;
            border-radius: 23.08rpx;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218789339137908.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
        }
        .group_7 {
          flex: 1 1 332.69rpx;
          .waterfall-item_2 {
            padding: 15.38rpx 7.69rpx 26.92rpx 23.08rpx;
            border-radius: 23.08rpx;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218789649995571.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
          .section_9 {
            padding: 15.38rpx 7.69rpx 26.92rpx 23.08rpx;
            border-radius: 23.08rpx;
            overflow: hidden;
            background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218789951949805.png);
            background-size: 100% 100%;
            background-repeat: no-repeat;
          }
        }
        .space-y-180 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 346.15rpx;
          }
        }
        .section_7 {
          margin-right: 7.69rpx;
          padding: 9.62rpx 15.38rpx;
          background-color: #00000033;
          border-radius: 1921.15rpx;
          backdrop-filter: blur(19.23rpx);
          width: 109.62rpx;
        }
        .image_6 {
          width: 25rpx;
          height: 26.92rpx;
        }
        .font_7 {
          font-size: 23.08rpx;
          font-family: MiSans;
          line-height: 18.27rpx;
          color: #ffffff;
        }
        .waterfall-item_3 {
          margin-top: 15.38rpx;
        }
        .space-y-94 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 180.77rpx;
          }
        }
      }
      .group_5 {
        padding: 15.38rpx 0;
      }
      .space-x-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 23.08rpx;
        }
      }
    }
    .font_1 {
      font-size: 30.77rpx;
      font-family: MiSans;
      line-height: 28.85rpx;
      color: #1d2129;
    }
    .space-x-4 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 7.69rpx;
      }
      .image_10 {
        border-radius: 749.04rpx;
        width: 26.92rpx;
        height: 26.92rpx;
      }
    }
    .font_2 {
      font-size: 26.92rpx;
      font-family: MiSans;
      line-height: 25rpx;
      color: #86909c;
    }
    .image_3 {
      width: 15.38rpx;
      height: 23.08rpx;
    }
    .space-y-8 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 15.38rpx;
      }
      .font_8 {
        font-size: 26.92rpx;
        font-family: MiSans;
        line-height: 25rpx;
        color: #ffffff;
      }
      .font_9 {
        font-size: 23.08rpx;
        font-family: MiSans;
        line-height: 22.12rpx;
        color: #ffffff;
      }
      .text_8 {
        color: #ffffff;
        line-height: 23.08rpx;
      }
    }
    .font_4 {
      font-size: 23.08rpx;
      font-family: MiSans;
      line-height: 25rpx;
      color: #86909c;
    }
    .section_10 {
      background-color: #ffffff;
      overflow: hidden;
      .horiz-list {
        padding: 11.54rpx 0 11.54rpx 30.77rpx;
        overflow-x: auto;
        .horiz-list-item {
          flex: 1 0 auto;
          .section_14 {
            padding: 17.31rpx 17.31rpx 0;
            background-color: #00000033;
            backdrop-filter: blur(9.62rpx);
            .group_9 {
              margin-right: 7.69rpx;
              .text_9 {
                line-height: 17.31rpx;
              }
              .text_10 {
                line-height: 26.92rpx;
              }
            }
            .space-y-2 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 3.85rpx;
              }
            }
          }
        }
        .section_12 {
          padding-top: 161.54rpx;
          border-radius: 23.08rpx;
          overflow: hidden;
          background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218783665033374.png);
          background-size: 100% 100%;
          background-repeat: no-repeat;
          height: 246.15rpx;
        }
        .horiz-list-item_2 {
          flex-shrink: 0;
          margin-left: 23.08rpx;
          .section_15 {
            padding: 17.31rpx 0 17.31rpx 17.31rpx;
            background-color: #00000033;
            backdrop-filter: blur(9.62rpx);
            .space-y-4 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 7.69rpx;
              }
            }
          }
        }
        .section_13 {
          padding-top: 161.54rpx;
          border-radius: 23.08rpx 0 0 23.08rpx;
          overflow: hidden;
          background-image: url(https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/65143c8f5a7e3f0310d31d40/651521f19325da0011df308b/16959218784129229531.png);
          background-size: 100% 100%;
          background-repeat: no-repeat;
          width: 372.12rpx;
          height: 246.15rpx;
        }
        .space-x-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 15.38rpx;
          }
        }
        .image_7 {
          border-radius: 1651.92rpx;
          width: 50rpx;
          height: 50rpx;
        }
        .font_10 {
          font-size: 19.23rpx;
          font-family: MiSans;
          line-height: 18.27rpx;
          color: #ffffff;
        }
      }
    }
    .text_7 {
      opacity: 0.7;
    }
    .section_16 {
      padding-top: 11.54rpx;
      background-color: #ffffff;
      .list_2 {
        padding: 0 23.08rpx 11.54rpx;
        .list-item_2 {
          padding: 23.08rpx 46.15rpx 23.08rpx 123.08rpx;
          background-color: #f7f8fa;
          border-radius: 23.08rpx;
          .font_11 {
            font-size: 23.08rpx;
            font-family: MiSans;
            line-height: 18.27rpx;
            color: #86909c;
          }
          .image_9 {
            width: 19.23rpx;
            height: 30.77rpx;
          }
          .font_12 {
            font-size: 26.92rpx;
            font-family: MiSans;
            line-height: 42.31rpx;
            color: #1d2129;
          }
          .text_12 {
            width: 482.69rpx;
          }
          .font_13 {
            font-size: 23.08rpx;
            font-family: MiSans;
            line-height: 21.15rpx;
            color: #86909c;
          }
          .text_13 {
            margin-top: 11.54rpx;
          }
          .group_10 {
            margin-top: 38.46rpx;
          }
          .text_14 {
            margin-top: 11.54rpx;
          }
          .image_8 {
            border-radius: 1921.15rpx;
            width: 69.23rpx;
            height: 69.23rpx;
          }
          .pos {
            position: absolute;
            left: 30.77rpx;
            top: 15.38rpx;
          }
        }
      }
    }
    .section_11 {
      padding: 26.92rpx 30.77rpx 19.23rpx;
      background-color: #ffffff;
      .group_8 {
        margin-right: 3.85rpx;
      }
      .text_11 {
        line-height: 27.88rpx;
      }
    }
  }
</style>