<template>
	<div>
		<!--<scroller lock-x height="200px" @on-scroll-bottom="onScrollBottom" ref="scrollerBottom" :scroll-bottom-offst="200">-->
			<div class="movie box2" v-for="(pic,ind) in picture" :key="ind">
				<router-link :to="{name:'predetails',params:{mid:pic.mid}}">
					<img :src="pic.m_mainpic" alt="" class="pic"/>
					<img src="../assets/video.png" class="vimg" />
				</router-link>
				<div class="detail">
					<h3><router-link to="/a">{{pic.m_name}}</router-link></h3>
					<p>猫眼评分 <span style="color: #ffc600;">{{pic.m_socre}}</span></p><span class="buy">购票</span>
					<p>类型:{{pic.m_type}}</p>
					<p>导演：{{pic.m_director}}</p>
				</div>
				<!--<load-more tip="loading"></load-more>-->
			</div>
		<!--</scroller>-->
	</div>
</template>
<script>
	import { Tabbar, TabbarItem, Scroller, LoadMore } from 'vux'

	export default {
		components: {
			Tabbar,
			TabbarItem,
			Scroller,
			LoadMore
		},
		data() {
			return {
				showList1: true,
				scrollTop: 0,
				onFetching: false,
				bottomCount: 20
			}
		},
		props: ["picture"],
//		mounted() {
//			this.$nextTick(() => {
//				this.$refs.scrollerBottom.reset({
//					top: 0
//				})
//			})
//		},
//		methods: {
//			onScrollBottom() {
//				if(this.onFetching) { // do nothing
//				} else {
//					this.onFetching = true
//					setTimeout(() => {
//						this.bottomCount += 10
//						this.$nextTick(() => {
//							this.$refs.scrollerBottom.reset()
//						})
//						this.onFetching = false
//					}, 2000)
//				}
//			}
//			
//		}
	}
</script>

<style>
	/*.box2-wrap {
		height: 800px;
		overflow: hidden;
	}
	*/
	.movie {
		margin: 10px 0px;
		position: relative;
	}
	
	.movie .pic {
		width: 110px;
		height: 140px;
	}
	
	.movie .vimg {
    width: 30px;
    height: 30px;
    position: absolute;
    top: 50px;
    left: 40px;
}
	
	.movie .detail {
		display: inline-block;
		position: absolute;
		top: 5px;
		left: 130px;
		width: 260px;
	}
	
	.detail .buy {
		border-radius: 14px;
	    padding: 2px 12px;
	    display: inline-block;
	    margin-left: 12px;
	    text-align: center;
	    background: #f34d41;
	    color: #FFFFFF;
	    font-size: 14px;
	    position: absolute;
	    right: 51px;
	    top: 38px;
	}
	
	.detail>p {
		font-size: 14px;
		color: #333333;
		margin-top: 10px;
	}
	
	.detail a {
		color: #333333;
	}
</style>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       