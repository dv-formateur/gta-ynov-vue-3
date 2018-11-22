<template>
	<div>
		<full-calendar :config="config" :events="events"/>
	</div>	
</template>

<script>

import moment from "moment";
import json from '../data/data.json'
import { FullCalendar } from "vue-full-calendar";
import "fullcalendar/dist/fullcalendar.css";


export default {
	data () {
		return {
			users: json,
			config: {
				defaultView: "month"
			},
			events: [] 
		}
	},
	props: ['idUser'],
	name: 'Planning',
    components: {
		FullCalendar
	},
	
	created() {
		if(this.idUser!=null) {
			if (this.users[this.idUser].contrat == "alternant") {
				var actuel = moment(this.users[this.idUser].dateDeb)
				var fin = moment(this.users[this.idUser].dateFin)
				while (moment(actuel).isBefore(fin)) {

					if (moment(actuel).format('dddd') != "Sunday" && moment(actuel).format('dddd') != "Saturday") { //si pas un weekend
						this.events.push({
							title     : 'Test',
							start     : actuel,
							color  : 'green',
						})
					}
					actuel = moment(actuel).add(1, 'days'); 
				}
			}
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
	},

	mounted: function() {	
		
	}
}

</script>

<style scoped>

</style>
