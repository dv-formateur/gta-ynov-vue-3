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
						<b-form-select v-model="idUser" :options="options" @input="refresh" class="mb-3" />
						<full-calendar :config="config" :events="events"/>
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
	import json from '../data/data.json'
	import { FullCalendar } from "vue-full-calendar";
	import "fullcalendar/dist/fullcalendar.css";
	
	export default {
		data () {
			return {
				users: json,
				idUser: null,
				options: [],
				config: {
					defaultView: "month"
				},
				events: [] 
			}
		},
		name: 'Responsable',
		components: {
			AjoutSalarie,
			FullCalendar,
		},

		created() { 
			for (let index = 0; index < this.users.length; index++) {
				this.options.push({
					value: index,
					text: this.users[index].nom
				})
			}
		},

		methods: {
			refresh() {
				if(this.idUser!=null) {
					this.events = []
					for (let i = 0; i < this.users[this.idUser].conge.length; i++) {
						this.events.push({
							title     : 'Congé',
							start     : this.users[this.idUser].conge[i],
							color  : 'grey',
						})
					}

					for (let i = 0; i < this.users[this.idUser].absence.length; i++) {
						this.events.push({
							title     : 'Absence',
							start     : this.users[this.idUser].absence[i],
							color  : 'red',
						})
					}
					for (let i = 0; i < this.users[this.idUser].calendrier.length; i++) {
						this.events.push({
							title     : this.users[this.idUser].calendrier[i].title,
							start     : this.users[this.idUser].calendrier[i].start,
							end		  : this.users[this.idUser].calendrier[i].end,
							color  : 'cyan',
						})
					}
				}
			}
		},
    }
</script>

<style scoped>
    #responsable {
        padding: 20px;
        margin-top: 10px;
    }
</style>