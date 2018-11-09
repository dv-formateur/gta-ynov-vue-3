<template>
	<div>
		<table class="table" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<tbody>
				<tr>
					<td>Nom</td>
					<td>{{this.users[this.$parent.$parent.$parent.$parent.idNum].nom}}</td>
				</tr>
				<tr>
					<td>Date de naissance</td>
					<td>{{this.users[this.$parent.$parent.$parent.$parent.idNum].doB}}</td>
				</tr>
				<tr>
					<td>Adresse</td>
					<td>{{this.users[this.$parent.$parent.$parent.$parent.idNum].adresse}}</td>
				</tr>
				<tr>
					<td>Telephone</td>
					<td>{{this.users[this.$parent.$parent.$parent.$parent.idNum].telephone}}</td>
				</tr>
				<tr>
					<td>Email</td>
					<td>{{this.users[this.$parent.$parent.$parent.$parent.idNum].mail}}</td>
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
