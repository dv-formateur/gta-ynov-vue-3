<template>
	<div class="row justify-content-center mt-4">
		<div class="col-12">
			<h2>Informations personnelles</h2>
		</div>
		<div class="text-center col-md-6 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Nom</div>
			<input type="text" name="nom" v-model="input.nom" placeholder="Nom" />
        </div>
		<div class="text-center col-md-6 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Prenom</div>
			<input type="text" name="prenom" v-model="input.prenom" placeholder="Prenom" />
        </div>
		<div class="text-center col-md-3 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Date de naissance</div>
			<input type="date" name="doB" v-model="input.doB" placeholder="Date de naissance" />
        </div>
        <div class="text-center col-md-3 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Adresse</div>
			<input type="text" name="adresse" v-model="input.adresse" placeholder="Adresse" />
        </div>
        <div class="text-center col-md-3 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Telephone</div>
			<input type="text" name="telephone" v-model="input.telephone" placeholder="Telephone" />
        </div>
        <div class="text-center col-md-3 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Email</div>
			<input type="text" name="email" v-model="input.email" placeholder="Email" />
        </div>
		
		<div class="col-12">
			<br/>
			<h2>Informations contrat</h2>
		</div>
		<div class="text-center col-md-4 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Date de debut</div>
			<input type="date" name="dateDeb" v-model="input.dateDeb" placeholder="Début" />
        </div>
		<div class="text-center col-md-4 col-lg" style="padding:0px 0px" v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Date de fin</div>
			<input type="date" name="dateFin" v-model="input.dateFin" placeholder="Fin" />
        </div>
        <div class="text-center col-md-4 col-lg" style="padding:0px 0px"  v-if="this.$parent.$parent.$parent.$parent.idNum !== null">
			<div class="bg-info text-white" style="width:100%">Heures hebdo</div>
			<input type="text" name="heuresHebdo" v-model="input.heuresHebdo" placeholder="Heures hebdo" />
        </div>
		<div class="text-center col-12">
			<br/>
			<button v-on:click="ajout()">Ajouter l'employé</button>
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
			input: {
					nom: "",
					prenom: "",
					doB: "",
					adresse: "",
					telephone: "",
					email: "",
					heuresHebdo: "",
					dateDeb: "",
					dateFin: "",
				},
		}
	},
	name: 'AjoutSalarie',
	props: {},
	methods: {
        ajout() {
			if (this.input.nom != "" || this.input.prenom != "" || this.input.doB != "" || this.input.adresse != "" || 
			this.input.telephone != "" || this.input.email != "" || this.input.heuresHebdo != "" || this.input.dateDeb != "" || this.input.dateFin != "") {
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
