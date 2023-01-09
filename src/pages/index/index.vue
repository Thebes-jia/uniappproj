
<template>
	<view class="content">
		<z-pagging ref="paging" v-model="dataList" @query="queryList">
			<view class="ftitle">
				<text>健康资讯</text>
				<view class="goDetail">
					<view>详情<span style="font-size: 24rpx;">➔</span> </view>
				</view>
			</view>
			<view slot="top" style="display: flex;padding: 20rpx;">
				
				<view class="tab">
					<scroll-view class="tab-scroll" scroll-x>
						<view class="tab-scroll_box">
							<view v-for="(item,index) in list" :key="index" class="tab-scroll_item" >
								{{item.name}}
							</view>
						</view>
					</scroll-view>
					<view class="tab-icons">
						<uni-icons type="gear" size="26" color="#666"></uni-icons>
					</view>
					<tab :list="tabList" @tab="tab"></tab>
				</view>
			</view>
			<view class="list">
				<view class="listcard mode-image">
					<view class="listcard-image">
						<image src="/static/yiyuan.png"></image>
					</view>
					<view class="listcard-content_title">
						<text>约翰霍普金斯大学医院</text>
					</view>
					<view class="listcard-content_des">
						<view class="listcard-content_des-label">
							<view class="listcard-content_des-label-item" style="font-size: 18rpx;">
								2021/01/12 12:11:22
							</view>
							<a href="https://www.hopkinsmedicine.org/international/chinese/about-us/jhusom" style="font-size: 18rpx;">详情<span style="font-size: 24rpx;">➔</span></a>
						</view>
					</view>
				</view>
				<view class="listcard mode-image">
					<view class="listcard-image">
						<image src="/static/drink.png" mode="aspectFill"></image>
					</view>
					<view class="listcard-content_title">
						<text>高血压患者喝水有什么样的讲究？</text>
					</view>
				</view>
			</view>
	    </z-pagging>
	</view>
</template>

<script>
	import Clickt from '@/components/clickt.vue'	;
	export default {
		props:{
					mode:{
						type:String,
						default:'base'
					}
				},
		data() {
			return {
				dataList:[],
				list:[
					{
						name:'最新',
						},{
						name:'抗议',
						},{
						name:'三高',
						},{
						name:'活动',
						},
				]
			}
		},
		
		onLoad() {

		},
		methods: {
			
			tab({data,index}){
						//console.Log(data,index)
					}
		}
		
	}
</script>

<style >
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

    .ftitle{
		font-size: 35rpx;
		width: 100%;
		display: flex;
		flex-direction:row;
		justify-content: space-between;
		
	}
	
	.goDetail {
		font-size: 28rpx;
		color: gray;
		display: flex;
		align-items: center;
		position: absolute;
		right: 40rpx;
		top: 10rpx;
	}
	
	.tab{
		display: flex;
		width: 100%;
		weight:100rpx;
		margin:10rpx auto 10rpx;
		
	}
	
	.tab-scroll_box{
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		color: gray;
	}
	
	
	.list{
		display: flex;
		flex-direction: column;
		width: 100%;
		weight:100rpx;
		margin:0 10rpx 10rpx;
	}

	.listcard mode-image{
		width: 100%;
		height: 100%;

		margin:10rpx 35rpx 10rpx;
		background-color: red;
	}
	
	.listcard-image{
		
	}

    .listcard-content_des-label{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	
	.text-area {
		display: flex;
		justify-content: center;
	}
	
</style>
