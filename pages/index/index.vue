<template>
	<view class="container">
		<view class="wrapper">
			<view class="title">基础使用</view>
			<RectangleBadge  value="默认状态" @click="onBadgeClick">
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">点击事件</view>
			<RectangleBadge  :value="state" type="primary" @click="onBadgeClick">
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">设置类型</view>
			<RectangleBadge  value="已完成" type="success">
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">朴素样式</view>
			<RectangleBadge  value="已完成" type="success" plain>
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">朴素样式 + 边框</view>
			<RectangleBadge  value="已完成" type="success" plain border>
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">设置位置</view>
			<RectangleBadge  value="默认状态" position="tl">
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">最小宽度</view>
			<RectangleBadge  value="默认状态" minWidth="200rpx">
				<view class="content"></view>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">多个标签</view>
			<RectangleBadge  value="主要" position="tl" type="primary">
				<RectangleBadge  value="成功" position="tr" type="success">
					<RectangleBadge  value="警告" position="bl" type="warning">
						<RectangleBadge  value="失败" position="br" type="error">
							<view class="content"></view>
						</RectangleBadge>
					</RectangleBadge>
				</RectangleBadge>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">设置尺寸</view>
			<RectangleBadge  value="已确认" position="tl" type="primary" size="mini">
				<RectangleBadge  value="已完成" position="tr" type="success" size="default">
					<RectangleBadge  value="待评价" position="bl" type="warning" size="middle">
						<RectangleBadge  value="已拒绝" position="br" type="error" size="large">
							<view class="content"></view>
						</RectangleBadge>
					</RectangleBadge>
				</RectangleBadge>
			</RectangleBadge>
		</view>
		<view class="wrapper">
			<view class="title">自定颜色</view>
			<RectangleBadge  value="自定颜色" position="tl" :color="['#673AB7', '#EEEEEE']">
				<RectangleBadge  value="自定颜色" position="tr" :color="['#673AB7', '#EEEEEE']" plain>
					<RectangleBadge  value="自定颜色" position="bl" :color="['#673AB7', '#EEEEEE']" plain border>
						<view class="content"></view>
					</RectangleBadge>
				</RectangleBadge>
			</RectangleBadge>
		</view>
	</view>
</template>

<script setup>
	import { ref } from 'vue'
	import RectangleBadge from '@/uni_modules/hope-11-rectangle-badge/components/hope-11-rectangle-badge/rectangle-badge.vue'
	
	const state = ref({label: '请点击', value: 1})
	
	const onBadgeClick = (e) => {
		uni.showToast({
			title: e.value ? JSON.stringify(e) : e,
			icon: 'none'
		})
	}
</script>

<style lang="scss" scoped>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		.wrapper {
			width: calc(100% - 40rpx);
			margin: 20rpx 40rpx;

			.title {
				margin-bottom: 10px;
				font-weight: bold;
				display: flex;
				justify-content: center;
				align-items: center;
			}

			.content {
				position: relative;
				box-sizing: border-box;
				width: 100%;
				height: 200rpx;
				background-color: #ddd;

				.rectangle-badge-tr {
					top: 0;
					right: 0;
				}

				.rectangle-badge-br {
					bottom: 0;
					right: 0;
				}

				.rectangle-badge-tl {
					top: 0;
					left: 0;
				}

				.rectangle-badge-bl {
					bottom: 0;
					left: 0;
				}
			}

		}

	}
</style>