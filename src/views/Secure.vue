<template>
    <div id="secure">
        <b-container>
			<b-row>
				<b-col sm="6" md="10" lg="12" xl="12">
					<h1>Zone salarié</h1>
					<p>
						<b-card no-body>
							<b-tabs pills card>
								<b-tab title="Fiche salarié" active>
								<FicheSalarie></FicheSalarie>
								</b-tab>
								<b-tab title="Planning">
								<Planning></Planning>
								</b-tab>
								<b-tab title="Tableau de bord">
								<TableauDeBord></TableauDeBord>
								</b-tab>
							</b-tabs>
						</b-card> 
					</p>
				</b-col>
			</b-row>
		</b-container>
    </div>
</template>

<script>
	import FicheSalarie from '@/components/FicheSalarie.vue'
	import Planning from '@/components/Planning.vue'
	import TableauDeBord from '@/components/TableauDeBord.vue'
	export default {
		name: 'Secure',
		components: {
			FicheSalarie,
			Planning,
			TableauDeBord,
		},
    }
</script>

<style scoped>
    #secure {
        background-color: #FFFFFF;
        border: 1px solid #CCCCCC;
        padding: 20px;
        margin-top: 10px;
    }
</style>