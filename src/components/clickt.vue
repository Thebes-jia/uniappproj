<template>
	<view class="tab">
		<scroll-view class="tab-scroll" scroll-x>
			<view class="tab-scroll_box">
				<view v-for="(item,index) in list" :key="index" class="tab-scroll_item" 
				@click="ClickTab(item,index)":class="{active:activeIndex===index}">
					{{item.name}}
				</view>
			</view>
		</scroll-view>l
		<view class="tab-icons">
			<uni-icons type="gear" size="26" color="#666"></uni-icons>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return {
				activeIndex:0
				}
		},
		methods:{
			ClickTab(item,index){
							this.activeIndex=index,
							this.$emit('tab',{
								data:item,
								index:index
							})
						}
		}
		
		
	}
</script>

<style>
</style>