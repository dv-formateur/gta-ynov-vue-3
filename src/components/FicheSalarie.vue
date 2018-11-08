<template>
	<div class="hello">
		<table class="table" v-if="this.users !== null">
			<tbody>
				<tr>
					<td>Nom</td>
					<td>{{this.users[0].nom}}</td>
				</tr>
				<tr>
					<td>Date de naissance</td>
					<td>{{this.users[0].doB}}</td>
				</tr>
				<tr>
					<td>Adresse</td>
					<td>{{this.users[0].adresse}}</td>
				</tr>
				<tr>
					<td>Telephone</td>
					<td>{{this.users[0].telephone}}</td>
				</tr>
				<tr>
					<td>Email</td>
					<td>{{this.users[0].mail}}</td>
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
