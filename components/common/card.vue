<template>
	<view class="px-2">
		<!-- header -->
		<view class="flex align-center border-bottom py-2">
			<image :src="headerImage" style="width: 40rpx;height: 40rpx;"></image>
			<view class="font-md ml-2">{{title }}</view>
		</view>
		<slot/>
		
	</view>
</template>

<script>
	export default {
		props:{
			title:{
				type:String,
				default:''
			},
			headerImage:{
				type:String,
				default:''
			}
		}
	}
</script>

<style>
</style>
