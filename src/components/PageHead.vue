<template>
	<div class="div">
		这个是页面顶部标题{{title}}
		{{name}}--{{age}}
		{{aa}}
	</div>
</template>

<script>
	// 通过import 导入外部js文件中定义的变量
	import {
		a
	} from '../assets/test1.js';
	export default {
		data() {
			return {
				aa: a
			}
		},
		//通过给子组件定义props属性, 可以实现父组件向子组件传值
		props: ['name', 'age']

	}
</script>


<style>
</style>
