<template>
  <div id="formulaire">
    <form>
      <v-text-field
        v-model="address.road"
        :counter="10"
        label="Road"
        required
        @input="$v.road.$touch()"
        @blur="$v.road.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="address.zipcode"
        label="Zipcode"
        required
        @input="$v.zipcode.$touch()"
        @blur="$v.zipcode.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="address.city"
        label="City"
        required
        @change="$v.city.$touch()"
        @blur="$v.city.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="address.complement"
        label="Complement"
        required
        @change="$v.complement.$touch()"
        @blur="$v.complement.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="address.country"
        label="Country"
        required
        @change="$v.country.$touch()"
        @blur="$v.country.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="address.state"
        label="State"
        required
        @change="$v.state.$touch()"
        @blur="$v.state.$touch()"
      ></v-text-field>

      <v-btn @click="submit">submit</v-btn>
      <v-btn @click="clear">clear</v-btn>
    </form>
  </div>
</template>


<script>
export default {
  name: 'mcAddressForm',
  props: {
    address: Object
  },
  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.road = '';
      this.zipcode = '';
      this.city = '';
      this.complement = '';
      this.country = '';
      this.state = '';
    },
  },
};
</script>

<style lang="stylus" scoped>
  #formulaire
    width: 300px;
    height: 300px
</style>

