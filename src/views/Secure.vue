<template>
    <div id="secure">
		<h1>Zone salarié</h1>
		<p>
			<b-card no-body>
				<b-tabs fill card>
					<b-tab title="Fiche salarié" active>
						<FicheSalarie :idUser="idUser"></FicheSalarie>
					</b-tab>
					<b-tab title="Planning">
						<Planning :idUser="idUser"></Planning>
					</b-tab>
					<b-tab title="Tableau de bord">
						<TableauDeBord :idUser="idUser"></TableauDeBord>
					</b-tab>
				</b-tabs>
			</b-card> 
		</p>
    </div>
</template>

<script>
	import FicheSalarie from '@/components/FicheSalarie.vue'
	import Planning from '@/components/Planning.vue'
	import TableauDeBord from '@/components/TableauDeBord.vue'
	export default {
		name: 'Secure',
		data () {
			return {
				idUser: this.$parent.idNum
			}
		},
		components: {
			FicheSalarie,
			Planning,
			TableauDeBord,
		},
	}
</script>

<style scoped>
    #secure {
        padding: 20px;
        margin-top: 10px;
    }
</style>