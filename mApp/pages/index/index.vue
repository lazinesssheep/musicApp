<template>
	<view class="index">
		<scroll-view :scroll-top="scrollTop" scroll-y="true" class="music-list">
			<template v-for="i in 10">
				<view :key="i" class="song">
					<!-- <audio :src="current.src" :poster="current.poster" :name="current.name" :author="current.author" :action="audioAction" controls></audio> -->
				</view>
			</template>
		</scroll-view>
		<view class="player">
			<audio :src="current.src" :poster="current.poster" :name="current.name" :author="current.author" :action="audioAction" controls></audio>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0,
				current: {
					poster: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/audio/music.jpg',
					name: '致爱丽丝',
					author: '暂无',
					src: '/static/mp3/123.mp3',
				},
				audioAction: {
					method: 'pause'
				}
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="less">
.index {
	.song {
		height: 150px;
		margin: 40upx;
		background-image: linear-gradient( 135deg, #81FFEF 10%, #F067B4 100%);
		box-shadow: 0px 0px 51px 0px rgba(0, 0, 0, 0.08), 0px 6px 18px 0px rgba(0, 0, 0, 0.05);
		transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1), box-shadow 0.35s cubic-bezier(0.4, 0, 0.2, 1);
		transform: translateY(0px);
	}
	.player {
		text-align: center;
	}
}
</style>
