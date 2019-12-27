<template>
	<view>
		<!-- 轮播 -->
		<new-swiper></new-swiper>
		<!-- 介绍 -->
		<new-table></new-table>
	</view>
</template>

<script>
	import newSwiper from '../compoutes/swiper.vue';
	import newTable from '../compoutes/newTable.vue';

	export default {
		components: {
			newTable,
			newSwiper
		},
		data() {
			return {

			};
		}

	}
</script>

<style>

</style>
