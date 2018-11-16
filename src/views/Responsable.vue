<template>
    <div id="responsable">
		<h1>Zone responsable</h1>
		<p>
			<b-card no-body>
				<b-tabs fill card>
					<b-tab title="Ajout de salarié" active>
						<AjoutSalarie></AjoutSalarie>
					</b-tab>
					<b-tab title="Planning equipe">

					</b-tab>
					<b-tab title="Récapitulatif infraction">

					</b-tab>
					<b-tab title="Information heure équipe">

					</b-tab>
				</b-tabs>
			</b-card> 
		</p>
    </div>
</template>

<script>
	import AjoutSalarie from '@/components/AjoutSalarie.vue'
	export default {
		name: 'Responsable',
		components: {
			AjoutSalarie,
		},
    }
</script>

<style scoped>
    #responsable {
        padding: 20px;
        margin-top: 10px;
    }
</style>