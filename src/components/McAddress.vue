<template>
  <div>
    <ul>
      <li>{{ address.road }}</li>
      <li>{{ address.zipcode }}</li>
      <li>{{ address.city | uppercase }}</li>
      <li v-if="address.complement">{{ address.complement }}</li>
      <li v-if="address.country">{{ address.country }}</li>
      <li v-if="address.state">{{ address.state }}</li>
    </ul>
		<div class="text-xs-center">
    	<v-btn round color="succes" @click="select">Edit</v-btn>
  	</div>
  </div>
</template>


<script>
export default {
  name: 'mcAddress',
  props: {
    address: Object,
  },
  methods: {
    select() {
      this.$emit('select', this.address);
    },
  },
  filters: {
    uppercase(value) {
      return value.toUpperCase();
    },
  },
};
</script>

<style lang="stylus" scoped>
	li
		list-style: none
	.text-xs-center
		margin-top: 30px
</style>

