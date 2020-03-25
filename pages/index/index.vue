<template>
	<view>
		<!-- 搜索框 -->
		<view class="cu-bar search bg-gradual-orange">
			<view class="search-form round">
				<!-- cuicon- 搜索图标 -->
				<text class="cuIcon-search"></text>
				<input v-model="search" placeholder="搜索想要的服装"></input>
			</view>
			<!-- 扫一扫 -->
			<view class="action">
				<text class="cuIcon-scan" style="font-size: 150%;"></text>
			</view>
		</view>
		<!-- 搜索框end -->
		<view>
			<!-- tab栏 -->
			<scroll-view scroll-x="true" class="nav bg-white">
				<view class="flex text-center">
					<!-- 循环遍历 数组   冒号代表动态  ：key获取索引值  动态判断thistab的值当值等于什么，相应的样式就变化-->
					<view :class="thistab == index?'text-orange cur' : ''" @click="qiehuan(index)" v-for="(item,index) in TabLists" :key="index" class="cu-item flex-sub">
						{{item}}
					</view>
				</view>
			</scroll-view>
		</view>
		<!-- tab栏end -->
		<!-- 轮播图 -->
		<!-- 获取图片下的小点，自动播放和衔接滑动 -->
		<swiper :indicator-dots="true" :autoplay="true" circular="true">
			<swiper-item>
				<image mode="scaleToFill" class="swiperimg" src="../../static/jpg/护眼模式_20190622220944.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image mode="scaleToFill" class="swiperimg" src="../../static/jpg/护眼模式_20190624234723.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image mode="scaleToFill" class="swiperimg" src="../../static/jpg/护眼模式_20190724083619.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image mode="scaleToFill" class="swiperimg" src="../../static/jpg/护眼模式_20190803091345.jpg"></image>
			</swiper-item>
		</swiper>
		<!-- 轮播图结束 -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				shu:null,
				search:"",
				thistab:0,
				TabLists:["男装","女装","运动","配饰","鞋"]
			}
		},
		onLoad() {

		},
		methods: {
			qiehuan(index){
				// console.log(index)
				this.thistab = index;
			}
		}
	}
</script>

<style>
	.swiperimg{
		width: 750upx;
		height: 300upx;
	}
</style>
