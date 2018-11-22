<template>
	<div class="row justify-content-center mt-4" v-if="this.idUser!=undefined">
		<div class="text-center col-md-5 col-lg" style="padding:0px 0px" v-if="this.idUser !== null">
			<div class="bg-info text-white" style="width:100%">Nom</div>
			{{this.users[this.idUser].nom}}
        </div>
		<div class="text-center col-md-5 col-lg" style="padding:0px 0px" v-if="this.idUser !== null">
			<div class="bg-info text-white" style="width:100%">Date de naissance</div>
			{{this.users[this.idUser].doB}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.idUser !== null">
			<div class="bg-info text-white" style="width:100%">Adresse</div>
			{{this.users[this.idUser].adresse}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.idUser !== null">
			<div class="bg-info text-white" style="width:100%">Telephone</div>
			{{this.users[this.idUser].telephone}}
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.idUser !== null">
			<div class="bg-info text-white" style="width:100%">Email</div>
			{{this.users[this.idUser].mail}}
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
	props: ['idUser'],
	created() {
		
	},
	mounted: function() {

	}
}

</script>

<style scoped>

</style>
