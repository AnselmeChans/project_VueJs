<template>
	<div class="search">

		<div class="flex-container">
			<div>
				<h1> FROM </h1>
				<mcAddress :address="from" @select="updateAddressToEdit"></mcAddress>
			</div>

			<div>
				<h1> TO </h1>
				<mcAddress :address="to" @select="updateAddressToEdit"></mcAddress>
			</div>
			<div>
				<h1> FORMULAIRE </h1>
				<mcAddressForm v-if="addressToEdit" :address="addressToEdit"></mcAddressForm>
		</div>
	</div>
	
	<div>
		<div class="mapping">
			<h1 > MAP </h1>
			<mcMap></mcMap>
		</div>
		
		<div class="affichCoord">
			<h1 style="margin-bottom: 100px"> AFFICHAGE COORDONEES </h1>
			<nominatimDataExtract :coordata="result"></nominatimDataExtract>
		</div>
	</div>
	
</div>


</template>


<script>

import mcAddressForm from '@/components/McAddressForm.vue';
import mcAddress from '@/components/McAddress.vue';
import mcMap from '@/components/McMap.vue';
import nominatimDataExtract from '@/components/NominatimDataExtract.vue'
import axios from "axios";

export default {
  name: 'search',
  components: {
		mcAddressForm,
		mcAddress,
		mcMap,
		nominatimDataExtract,
		
	},
	data(){
		return {
			from: {
				road: "2, rue Riquet",
				zipcode: "31",
				city: "Paris",
				complement: "",
				country: "",
				state: ""
			},
			to: {
				road: "3, rue Matabiau",
				zipcode: "31000",
				city: "Madrid",
				complement: "",
				country: "Esp",
				state: ""
			},
			addressToEdit: {     
				},
			result: null, 
			coord: null
		};
	},
	methods: {
    updateAddressToEdit(address) {
      this.addressToEdit = address;
    },
	},
	
	created() {
		axios
			.get("http://nominatim.openstreetmap.org/search/toulouse?format=json")
			.then(response => {
				this.result = response.data
			})
			.catch(error => {
				console.log(error)
			});
		}
	};
</script>

<style lang="stylus" scoped>
	.flex-container
		display: flex
		justify-content: center
		
	.flex-container div 
		margin : 60px

	.mapping
		margin-top: 100px;
		
	
</style>

