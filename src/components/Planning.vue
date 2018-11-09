<template>
	<full-calendar :events="events" />
</template>

<script>
//export default {

import json from '../data/data.json'
import FullCalendar from 'vue-fullcalendar';
export default {
	data () {
		return {
			users: json,
			events: [] 
		}
	},
	name: 'Planning',
    components: {
		FullCalendar
	},
	
	created() {
		if(this.$parent.$parent.$parent.$parent.idNum!=null) {
			for (let i = 0; i < this.users[this.$parent.$parent.$parent.$parent.idNum].conge.length; i++) {
				this.events.push({
					title     : 'Congé',
					start     : this.users[this.$parent.$parent.$parent.$parent.idNum].conge[i],
					cssClass  : 'blue',
				})
			}

			for (let i = 0; i < this.users[this.$parent.$parent.$parent.$parent.idNum].absence.length; i++) {
				this.events.push({
					title     : 'Absence',
					start     : this.users[this.$parent.$parent.$parent.$parent.idNum].absence[i],
					cssClass  : 'blue',
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
