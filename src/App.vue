<template>
	<!-- 页面顶部-->
	<div class="head-box">
		<!-- 使用组件时，通过属性给子组件传递数据 -->
		<PageHead :name='title' :age="number"></PageHead>

	</div>
	<div class="main">
		<!-- 页面左边 -->
		<div class="left-box">
			<!-- 监听自定义的事件 -->
			<LeftBox @updateCount='handleLeftCount' @update2='handleLeftCount2'></LeftBox>
		</div>
		<!-- 页面右边 -->
		<div class="right-box">
			<RightBox></RightBox>
		</div>
	</div>


</template>

<script>
	import PageHead from './components/PageHead.vue';
	import LeftBox from './components/LeftBox.vue';
	import RightBox from './components/RightBox.vue';
	export default {
		name: 'App',
		components: {
			PageHead,
			LeftBox,
			RightBox,

		},
		data() {
			return {
				title: '标题啊啊啊啊啊啊啊啊',
				n: 100
			}
		},
		computed: {
			number() {
				return this.n * 10
			},

		},
		methods: {
			handleLeftCount(count) {
				// alert('监听到了updateCount事件')
				// console.log(arguments)
				console.log('子组件通过事件传递过来的参数 :count,', count)
			},
			handleLeftCount2(count, name) {
				console.log('子组件传递的其他参数:count,age', count, name)

			}
		}

	}
</script>

<style>
	.head-box {
		height: 70px;
		background-color: bisque;
	}

	.main {
		display: flex;
	}

	.left-box {
		width: 400px;
		height: 800px;
		background-color: aqua;
		flex: 1;
	}

	.right-box {
		width: 300px;
		height: 800px;
		background-color: brown;
		flex: 1;
	}
</style>
