<template>
	<div class="row justify-content-center mt-4">
		<!-- v-for chaque salarie
			 Solde d’annualisation
Solde de congés
Solde d’absence (en heures et en jours), avec le détail des motifs d’absence
 -->
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
	name: 'HeureEquipe',
	props: {},
	methods: {
        ajout() {
			if (this.input.nom != "" || this.input.prenom != "" || this.input.doB != "" || this.input.adresse != "" || this.input.telephone != "" ||
				this.input.email != "" || this.input.heuresHebdo != "" || this.input.dateDeb != "" || this.input.dateFin != "") {
				return 1
			}
			//eslint-disable-next-line
            console.log("Ajout du salarié");
        }
    },
}

</script>

<style scoped>

</style>
