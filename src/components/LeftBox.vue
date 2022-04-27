<template>
	<div>
		左侧盒子
	</div>
	<button type="button" @click="count--">-</button>
	<input type="text" v-model="count">
	<button type="button" @click="count++">+</button>
	<hr>
	<button type="button" @click="$emit('updateCount',count)">updateCount事件</button>
	<button type="button" @click="work">updateCount事件</button>
	<button type="button" @click="work2">update2事件</button>



</template>

<script>
	export default {
		data() {
			return {
				count: 0,
				name: 'haha'
			};
		},
		//通过emits定义事件
		emits: ['updateCount', 'update2'],
		methods: {
			work() {
				//通过$emit触发自定义的事件,可以实现子组件向父组件传值(可以传递多个值)
				this.$emit('updateCount', this.count)
			},
			work2() {
				this.$emit('update2', this.count, this.name)
			}

		}
	}
</script>

<style>
</style>
