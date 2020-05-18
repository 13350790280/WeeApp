<template>
	<view>
		<!-- 常用分类 card -->
		<card :title="cardList.title" :headerImage="cardList.src">
			<view class="row ">
				<block v-for="(item, index) in cardList.list" :key="index"><bottom-style :item="item" @click="clickItem"></bottom-style></block>
			</view>
		</card>
	</view>
</template>

<script>
import card from '@/components/common/card.vue';
import bottomStyle from '@/components/common/bottom-style.vue';
export default {
	components: {
		bottomStyle,
		card
	},
	data() {
		return {
			cardList: {
				src: '/static/tab-cate.png',
				title: '常用分类',
				list: ['衣服100', '帽子22', '衣服34', '帽子4', '衣服5', '帽子6', '衣服7', '帽子8', '衣服9']
			},
			// 搜索内容
			seachText: ''
		};
	},
	methods: {
		// 点击分类
		clickItem(item) {
			this.seachText = item;
			this.$api.msg('搜索-----' + this.seachText);
		}
	},
	// #ifndef MP
	// 输入框
	onNavigationBarSearchInputChanged(e) {
		// console.log(e.text);
		this.seachText = e.text;
	},
	//点击导航栏 buttons 时触发
	onNavigationBarButtonTap(e) {
		const index = e.index;
		if (index === 0) {
			this.$api.msg('搜索---' + this.seachText);
		}
	}
	// #endif
};
</script>

<style></style>
