<template>
	<div class="hello">
		<table class="table" v-if="this.users !== null">
			<tbody>
				<tr>
					<td>Date de début</td>
					<td>{{this.users[0].dateDeb}}</td>
				</tr>
				<tr>
					<td>Date de fin</td>
					<td>{{this.users[0].dateFin}}</td>
				</tr>
				<tr>
					<td>Nombre d'heures hebdomadaires</td>
					<td>35</td>
				</tr>
				<tr>
					<td>Solde de congé</td>
					<td>TBD</td>
				</tr>
				<tr>
					<td>Bilan d'annualisation</td>
					<td>TBD</td>
				</tr>
			</tbody>
		</table>
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
