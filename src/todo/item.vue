<template lang="html">
	<div :class="['todo-item',todo.completed?'completed':'']">
		<div class="checkboxWrapper theme2 smallCheckboxSize">
			<input type="checkbox" id="finished-checkbox" v-model="todo.completed">
			<label for="finished-checkbox">
				<i>
					<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
				width="50px" height="50px" viewBox="0 0 50 50" enable-background="new 0 0 50 50" xml:space="preserve">
					<circle fill="none" stroke="#B7B7B7" stroke-width="3" stroke-miterlimit="10" cx="25.11" cy="24.883" r="23.519"></circle>
					<path fill="none" stroke-width="3" stroke-miterlimit="10" d="M48.659,25c0,12.998-10.537,23.534-23.534,23.534
					S1.591,37.998,1.591,25S12.127,1.466,25.125,1.466c9.291,0,17.325,5.384,21.151,13.203L19,36l-9-14"></path>
				</svg>
				</i>
				{{todo.content}}
			</label>
			<span class="destroy close rounded thick" @click="deleteTodo"></span>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			todo: {
				type: Object,
				required: true
			}
		},
		methods: {
			deleteTodo() {
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.todo-item
		position relative
		background #ffffff
		font-size 24px
		border-bottom 1px solid rgba(0, 0, 0, .06)
		&:hover
			.destroy::before, .destroy::after
				display: block

		label
			float left
			width 80%
			white-space normal
			word-break break-all
			padding 15px 15px 15px 15px
			margin-left 45px
			display block
			line-height 1
			transition color 0.4s

	&.completed
		label
		color #d9d9d9
		text-decoration line-through

	.destroy::before, .destroy::after
		display: none

</style>