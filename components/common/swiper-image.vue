<template>
	<view>
		<swiper class="carousel" circular autoplay @change="swiperChange">
			<swiper-item v-for="(item, index) in carouselList" :key="index" class="carousel-item" @click="$emit('click' ,{title: '轮播广告'})">
				<image :src="item.src" />
			</swiper-item>
		</swiper>
		<!-- 自定义swiper指示器 -->
		<view class="swiper-dots">
			<text class="num">{{swiperCurrent+1}}</text>
			<text class="sign">/</text>
			<text class="num">{{swiperLength}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			carouselList:Array,
			swiperCurrent:{
				type:[String,Number],
				default:0
			},
			swiperLength:{
				type:[String,Number],
				default:0
			}
		},
		methods:{
			swiperChange(e){
				this.$emit('swiperChange',e)
			}
		}
	}
</script>

<style>
	
</style>
