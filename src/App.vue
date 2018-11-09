<template>
    <div id="app">
        <div id="nav">
            <router-link v-if="authenticated" to="/login" v-on:click.native="logout()" replace>Logout</router-link>
        </div>
        <router-view @authenticated="setAuthenticated" />
    </div>
</template>

<script>
	import Vue from 'vue'
	import BootstrapVue from 'bootstrap-vue'

	Vue.use(BootstrapVue);
	import 'bootstrap/dist/css/bootstrap.css'
	import 'bootstrap-vue/dist/bootstrap-vue.css'
</script>

<script>
	import json from './data/data.json'
    export default {
        name: 'App',
        data() {
            return {
                authenticated: false,
				users: json,
				identifiants: [],
				motdepasses: [],
				idNum: null,
            }
        },
        mounted() {
            if(!this.authenticated) {
                this.$router.replace({ name: "login" });
			}
			
			for (let i = 0; i < this.users.length; i++) {
				this.identifiants.push(this.users[i].id)
				this.motdepasses.push(this.users[i].mdp)
			}
		},
		
        methods: {
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
        }
    }
</script>

<style>
    body {
        background-color: #F0F0F0;
    }
    h1 {
        padding: 0;
        margin-top: 0;
    }
    #app {
        width: 1024px;
        margin: auto;
    }
</style>