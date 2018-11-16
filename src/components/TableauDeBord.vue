<template>
	<div class="row justify-content-center mt-4">
		<div class="text-center col-md-5 col-lg" style="padding:0px 0px" v-if="this.users[this.$parent.$parent.$parent.$parent.idNum] !== null">
			<div class="bg-info text-white" style="width:100%">Date de début</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].dateDeb}}
        </div>
		<div class="text-center col-md-5 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Date de fin</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].dateFin}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Heures hebdo</div>
			TBD
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Solde de congé</div>
			TBD
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Bilan d'annualisation</div>
			TBD
        </div>
	</div>
</template>

<script>
//export default {

import json from '../data/data.json'
export default {
	data () {
		return {
			users: json,
		}
	},
	name: 'TableauDeBord',
	props: {},
	created() {

	},
	mounted: function() {

	}
}

</script>

<style scoped>

</style>
