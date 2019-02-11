<template>
	<div class="hello">
		<h1> {{msg}} </h1>
	</div>
</template>

<script>
export default {
  name: 'helloAcceuil',
  props: {
    msg: String,
  },
};
</script>

<style lang="stylus" scoped>
	.hello
		margin-top: 100px

</style>
