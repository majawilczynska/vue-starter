<template>
  <div>
	  <h1>Witaj w systemie do zapisów na zajęcia</h1>
	  <div v-if="authenticated">
		  <h2>Witaj {{email}} !</h2>
	    <a @click="logOut()">Wyloguj</a>
	  </div>
	  <div v-else>
		Zaloguj się e-mailem
		  <input type="text" v-model="email">
		  <button @click="logIn()">Wchodzę</button>
	  </div>
  </div>
</template>

<script>
import "milligram";

export default {
	data() {
	  return {
		authenticated: false,
		email: ''
	  };
	},
	methods: {
		logIn() {
			this.authenticated = true;
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
