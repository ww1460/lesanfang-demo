<template>
	<view class="newTab">
		<scroll-view scroll-x class="nav" scroll-with-animation :scroll-left="scrollLeft">
			<view class="cu-item" :class="index==TabCur?'text-blue cur':''" v-for="(item,index) in tabList" :key="index" @tap="tabSelect"
			 :data-id="index">
				{{item}}
			</view>
			<view class="tab-right">
				<view>
					<image src="../../static/images/筛选.png" class="tabImg"></image>
				</view>
				<view>
					筛选
				</view>
			</view>
		</scroll-view>
		<!-- 全部 -->
		<view v-for="(item,index) in allList" :key="index" v-if="TabCur == '0'">
			<view class="cu-card case" style="border-radius:14px ;">
				<view class="cu-item shadow" style="display: flex;">
					<view class="image card-list">
						<image src="../../static/images/man.jpg" class="img" @tap="goDetails(index)"></image>
					</view>
					<view class="shadow-right">
						<view style="width:95%">
							<view class="name_pos">
								<view>
									<text style="color:#000000;font-size: 1rem
									;font-weight: 600;">{{item.name}}</text>
								</view>
								<view>
									<image src="../../static/images/距离定位.png" class="postion">100米</image>
								</view>
							</view>
							<view class="info">
								<text>{{item.area}}</text>
								<text class='line'>|</text>
								<text>{{item.age}}岁</text>
								<text class='line'>|</text>
								<text>{{item.experience}}</text>
								<text class='line'>|</text>
								<text>{{item.education}}</text>
							</view>
							<view class="">
							</view>
							<view>
								<text class="occupation">工程师</text>
								<text class="occupation">web</text>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 工程师 -->
		<view v-for="(item,index) in engineerList" :key="index" v-if="TabCur == '1'">
			<view class="cu-card case" style="border-radius:14px ;">
				<view class="cu-item shadow" style="display: flex;">
					<view class="image card-list">
						<image src="../../static/images/man.jpg" class="img" @tap="goDetails(index)"></image>
					</view>
					<view class="shadow-right">
						<view style="width:95%">
							<view class="name_pos">
								<view>
									<text style="color:#000000;font-size: 1rem
									;font-weight: 600;">{{item.name}}</text>
								</view>
								<view>
									<image src="../../static/images/距离定位.png" class="postion">100米</image>
								</view>
							</view>
							<view class="info">
								<text>{{item.area}}</text>
								<text class='line'>|</text>
								<text>{{item.age}}岁</text>
								<text class='line'>|</text>
								<text>{{item.experience}}</text>
								<text class='line'>|</text>
								<text>{{item.education}}</text>
							</view>
							<view class="">
							</view>
							<view>
								<text class="occupation">工程师</text>
								<text class="occupation">web</text>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- web前端 -->
		<view v-for="(item,index) in webList" :key="index" v-if="TabCur == '2'">
			<view class="cu-card case" style="border-radius:14px ;">
				<view class="cu-item shadow" style="display: flex;">
					<view class="image card-list">
						<image src="../../static/images/man.jpg" class="img" @tap="goDetails(index)"></image>
					</view>
					<view class="shadow-right">
						<view style="width:95%">
							<view class="name_pos">
								<view>
									<text style="color:#000000;font-size: 1rem
									;font-weight: 600;">{{item.name}}</text>
								</view>
								<view>
									<image src="../../static/images/距离定位.png" class="postion">100米</image>
								</view>
							</view>
							<view class="info">
								<text>{{item.area}}</text>
								<text class='line'>|</text>
								<text>{{item.age}}岁</text>
								<text class='line'>|</text>
								<text>{{item.experience}}</text>
								<text class='line'>|</text>
								<text>{{item.education}}</text>
							</view>
							<view class="">
							</view>
							<view>
								<text class="occupation">工程师</text>
								<text class="occupation">web</text>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				TabCur: 0,
				scrollLeft: 0,
				tabList: ["全部", "工程师", "WEB前端"],
				allList: [{
					name: "刘晓伟",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}, {
					name: "刘晓伟",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}, {
					name: "刘晓伟",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}],
				engineerList: [{
					name: "adasd",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}, {
					name: "2wqr",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}],
				webList: [{
					name: "wegwe",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}, {
					name: "wegweg",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}, {
					name: "wegweg",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}, {
					name: "ewgwe",
					area: "日本",
					age: "30",
					experience: "8年左右",
					education: "本科"
				}]
			}
		},
		methods: {
			tabSelect(e) {
				this.TabCur = e.currentTarget.dataset.id;
				this.scrollLeft = (e.currentTarget.dataset.id - 1) * 60
			},
			goDetails(val) {
				uni.navigateTo({
					url: '../list/list?&type=求职&id=' + val
				})
			}
		}
	}
</script>

<style scoped>
	.newTab .tab-right {
		float: right;
		display: flex;
		align-items: center;
		margin-right: 10px;
	}

	.newTab .tabImg {
		width: 2rem;
		height: 2rem;
	}

	.newTab .card-list {
		background: #FFFFFF;
		width: 33%;
		height: 6rem;
		justify-content: center;
		/*子元素水平居中*/
		align-items: center;
		/*子元素垂直居中*/
		display: -webkit-flex;
	}

	.newTab .card-list .img {
		width: 5rem;
		height: 5rem;
		border-radius: 0.4rem;
		/* margin: 8px */
		justify-content: center;
		/*子元素水平居中*/
		align-items: center;
		/*子元素垂直居中*/
		display: -webkit-flex;
	}

	.newTab .shadow-right {
		width: 67%;
		justify-content: center;
		/*子元素水平居中*/
		align-items: center;
		/*子元素垂直居中*/
		display: -webkit-flex;
	}

	.occupation:first-child {
		margin-left: 0px;
	}

	.occupation {
		display: inline-block;

		line-height: 1.1rem;
		background: #f4f4f4;
		margin-right: 10px;
		text-align: center;
		padding: 0px 5px;
		font-size: 1rem;
	}

	.postion {
		width: 1rem;
		height: 1rem;
	}

	.name_pos {
		display: flex;
		justify-content: space-between;
	}

	.line {
		padding: 0px 5px;
	}

	.info {
		margin: 8px 0px;
		color: #999999
	}
</style>
