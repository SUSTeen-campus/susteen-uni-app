<template>
	<view class="flex-col page">
		<view class="feedback">
			<textarea v-model="feedback" @input="debouncedFeedback"
				placeholder="期待您的反馈与建议，SUSTEEN将不断优化改进以提升您的体验（50字以内）"></textarea>
		</view>

		<view class="contact">
			<input type="text" v-model="contact" @input="debouncedContact" placeholder="请留下您的电话或邮箱" />
		</view>

		<view class="flex submit items-center justify-center">
			<view class="flex wrapper items-center justify-center" @click="handleSubmit"> 
				<text>提   交</text>
			</view>
		</view>
	</view>



</template>

<script>
	import debounce from 'lodash.debounce';

	export default {
		components: {},
		props: {},
		data() {
			return {
				feedback: '',
				contact: '',
			};
		},

		methods: {
			// 使用lodash.debounce创建防抖函数
			debouncedFeedback: debounce(function() {
				// 处理feedback的逻辑
				// console.log('Feedback:', this.feedback);
			}, 500), // 500毫秒延迟

			debouncedContact: debounce(function() {
				// 处理contact的逻辑
				// console.log('Contact:', this.contact);
			}, 500), // 500毫秒延迟
			
			handleSubmit() {
				
			}
		},
	};
</script>

<style scoped lang="scss">
	.feedback {
		display: flex;
		margin: 30rpx 30rpx;
		height: 400rpx;
		border: solid 2rpx #b0b1b1;
		border-radius: 10rpx;
		padding: 5rpx 10rpx;
	}

	.contact {
		display: flex;
		margin: 0rpx 30rpx;
		height: 80rpx;
		border: solid 2rpx #b0b1b1;
		border-radius: 10rpx;
		padding: 5rpx 10rpx;
	}

	.submit {
		
		height: 100rpx;
		margin-top: 30rpx;
		backdrop-filter: blur(20rpx);
		border: solid 2rpx #e5e6eb;
		
		.wrapper {
			height: 80%;
			width: 300rpx;
			background-color: #34c759;
			border-radius: 10rpx;
			
			text {
				color: #ffffff;
				font-size: 35rpx;
			}
		}
		
	}
	textarea::placeholder {
		font-size: 35rpx;
		color: #b0b1b1;
		font-family: MiSans;
	}
	
	input::placeholder {
	  font-size: 35rpx;
	  color: #b0b1b1;
	  font-family: MiSans;
	}

</style>