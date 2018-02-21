<template lang="html">
	<div id="main-footer">
		Witten by {{author}}
	</div>
</template>

<script>
	export default {
		data() {
			return {
				author: "Jason"
			}
		},
		components: {}
	}
</script>

<style lang="stylus" scoped>
	#main-footer {
		margin-top 40px
		text-align center
		color #ffffff
		font-size 30px
	}
</style>