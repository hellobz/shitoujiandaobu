<template>
	<view class="content">
		<view class="game_wrap" v-if="game === 0">
			<image class="game_photo" src="../../static/剪刀.png" mode=""></image>
		</view>
		<view class="game_wrap" v-else-if="game === 1">
			<image class="game_photo" src="../../static/石头.png" mode=""></image>
		</view>
		<view class="game_wrap" v-else-if="game === 2">
			<image class="game_photo" src="../../static/布.png" mode=""></image>
		</view>
		<button class="btn" type="primary" @click="handleContrast">比一比</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				game: ''
			}
		},
		onLoad() {

		},
		methods: {
			handleContrast() {
				this.game = Math.floor(Math.random()*3)
				// console.log(this.game)
				if(this.game === 0) {
					uni.showToast({
						title: '你的是剪刀'
					})
				}else if (this.game === 1) {
					uni.showToast({
						title: '你的是石头'
					})
				}else if (this.game === 2) {
					uni.showToast({
						title: '你的是布'
					})
				}
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.game_photo {
		width: 240rpx;
		height: 240rpx;
	}
	
	.game_wrap {
		margin-top: 130rpx;
	}
	
	.btn {
		margin-top: 100rpx;
	}
</style>
