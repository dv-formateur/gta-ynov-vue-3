<template>
    <div id="login">
        <h1>Login</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <input type="password" name="password" v-model="input.password" placeholder="Password" />
        <button type="button" v-on:click="login()">Login</button>
    </div>
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    username: "resp",
                    password: "resp"
				},
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
					for (let index = 0; index < this.$parent.identifiants.length; index++) {
						if(this.input.username == this.$parent.identifiants[index] && this.input.password == this.$parent.motdepasses[index]) {
							this.$parent.idNum = index
							this.$emit("authenticated", true);
							if (this.$parent.users[index].role == "salarie") {
								this.$router.replace({ name: "secure" });								
							} else {
								this.$router.replace({ name: "responsable"})
							}
						}
					}
                } else {
					//eslint-disable-next-line
                    console.log("A username and password must be present");
                }
            }
        }
    }
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }
</style>