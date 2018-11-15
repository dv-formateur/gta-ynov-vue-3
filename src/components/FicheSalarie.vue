<template>
	<div class="row justify-content-center mt-4">
		<div class="text-center col-md-5 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-primary text-white" style="width:100%">Nom</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].nom}}
        </div>
		<div class="text-center col-md-5 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-primary text-white" style="width:100%">Date de naissance</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].doB}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-primary text-white" style="width:100%">Adresse</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].adresse}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-primary text-white" style="width:100%">Telephone</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].telephone}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-primary text-white" style="width:100%">Email</div>
			{{this.users[this.$parent.$parent.$parent.$parent.idNum].mail}}
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
	name: 'FicheSalarie',
	props: {},
	created() {
		
	},
	mounted: function() {

	}
}

</script>

<style scoped>

</style>
