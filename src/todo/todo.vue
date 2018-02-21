<template lang="html">
	<section class="real-app">
		<input type="text"
					 class="add-input"
					 autofocus="autofocus"
					 placeholder="请添加一个事项"
					 @keyup.enter="addTodo"
		/>
		<item :todo="todo"
			v-for="todo in todos"
		  :key="todo.id"
		  @del="deleteTodo"/>
		<tabs :filter="filter"/>
	</section>
</template>

<script>
	import Item from './item.vue'
	import Tabs from './tabs.vue'
	let id = 0;

	export default {
		data() {
			return {
				todos:[],
				filter: 'All'
			}
		},
		components: {
			Item,
			Tabs
		},
		methods: {
			addTodo(e) {
				this.todos.unshift({
					id: id++,
					content: e.target.value.trim(),
					completed: false
				})
				e.target.value = ''
			},
			deleteTodo(id) {
				this.todos.splice(this.todos.findIndex(todo => todo.id === id), 1)
			}
		}
	}
</script>

<style lang="stylus" scoped>
.real-app {
	width 600px
	margin 0 auto
	box-shadow 0 0 5px #666
}
.add-input {
	positon:relative;
	margin 0
	width 100%
	font-size 24px
	font-family  inherit
	font-weight:inherit
	line-height 1.4rem
	border 0;
	outline none
	color inherit
	box-shadow: inset 0 -1px 5px 0px rgba(0,0,0,0)
	box-sizing border-box
	font-smoothing:antialiased;
	padding 16px 16px 16px 60px
	border none
}
</style>