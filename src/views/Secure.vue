<template>
    <div id="secure">
        <h1>Secure Area</h1>
        <p>
            <b-card no-body>
				<b-tabs pills card>
					<b-tab title="Fiche salarié" active>
					<FicheSalarie></FicheSalarie>
					</b-tab>
					<b-tab title="Planning">
					Tab Contents 2
					</b-tab>
					<b-tab title="Tableau de bord">
					<TableauDeBord></TableauDeBord>
					</b-tab>
				</b-tabs>
			</b-card> 
        </p>
    </div>
</template>

<script>
	import FicheSalarie from '@/components/FicheSalarie.vue'
	import TableauDeBord from '@/components/TableauDeBord.vue'
	export default {
		name: 'Secure',
		components: {
			FicheSalarie,
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