<template>
	<view class="content">
		<view class="main-chick">
			<view class="main-title">
				<view class="title-icon">
					<img src="../../static/title-icon.png" alt="">
				</view>
				<view>Orix Mechanics</view>
				<view>@just one app about mechanics</view>
			</view>
			<view class="main-icon">
				<img src="../../static/icon.png" alt="">
			</view>
			<view class="main-bottom">
				<swiper indicator-dots="true" autoplay="true" circular="true"> 
					<swiper-item>
						<view>Machinery</view>
						<view>Machinery is a combination of objects, and it is difficult to deform even if the pseudo force is applied to each part.</view>
					</swiper-item>
					<swiper-item>
						<view>Main Features</view>
						<view>Machinery is a combination of artificial physical components. Each part of the machine has a definite relative motion.</view>
					</swiper-item>
					<swiper-item>
						<view>机械</view>
						<view>机械是物体的组合，假定力加到其各个部分也难以变形;这些物体必须实现相互的、单一的、规定的运动.</view>
					</swiper-item>
				</swiper>
				<view class="wave-main">
					<button class="wave-btn" @click="onLogin" ref="logRef">Login In
						<span v-for="(item,idx) in logSpanList" :key="idx" :style="{ top: item.y + 'px', left: item.x + 'px' }">
						</span>
					</button>
					<button class="wave-btn" @click="onSign">Sign Up
						<span v-for="(item,idx) in signSpanList" :key="idx" :style="{top: item.y + 'px', left: item.x + 'px'}">
						</span>
					</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				logSpanList: [],
				signSpanList: []
			}
		},
		methods: {
			onLogin(e) {
				this.addWave(e,this.logSpanList)
			},
			onSign(e) {
				this.addWave(e,this.signSpanList)
			},
			addWave(e, list) {
				let waveX = e.detail.x - e.currentTarget.offsetLeft
				let waveY = e.detail.y - e.currentTarget.offsetTop
				setTimeout(() => {
					list.shift()
				},800)
				list.push({
					x: waveX,
					y: waveY
				})
			},
		}
	}
</script>
<style lang="less" scoped>
@import url(./index.less);
</style>
