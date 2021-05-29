<template>
  <div>
	  <h1>Witaj w systemie do zapisów na zajęcia</h1>
	  <div v-if="authenticated">
		  <h2>Witaj {{email}} !</h2>
	    <a @click="logOut()">Wyloguj</a>
	  </div>
	  <div v-else
		  <login-form @login="logIn($event)"></login-form>
	  </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
	components: {LoginForm},
	data() {
	  return {
		authenticated: false,
		email: ''
	  };
	},
	methods: {
		logIn(username) {
			this.authenticated = true;
			this.email = username;
		},
		logOut() {
			this.authenticated = false;
			this.email = '';
		}
	}
};
</script>

<style>

</style>
