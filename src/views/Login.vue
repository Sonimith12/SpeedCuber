<template>
	<div class="login-container">
	  <h1 class="login-heading">Login</h1>
	  <form @submit.prevent="login" class="login-form">
		<div class="form-group">
		  <label for="username" class="form-label">Email</label>
		  <input type="text" v-model="email" id="username" name="username" class="form-input" placeholder="Enter your username" required>
		</div>
		<div class="form-group">
		  <label for="password" class="form-label">Password</label>
		  <input type="password" v-model="password" id="password" name="password" class="form-input" placeholder="Enter your password" required>
		</div>
		<button type="submit" class="login-button">Login</button>
	  </form>
	  <div class="signup-link">
		Not yet registered? <RouterLink to="/signup" class="signup-link-text">Sign Up</RouterLink>
	  </div>
	</div>
  </template>
  
  <script>
  import axios from 'axios'
  export default {
	emits: ['checkout'],
	name: "Login",
	data() {
	  return {
		email: '',
		password: ''
	  }
	},
	methods: {
	  async login() {
		try {
		  let response = await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`);
		  console.warn(this.email, this.password);
		  this.$emit('checkout', { email: this.email, password: this.password });
		  console.warn(response);
		  if (response.status === 200 && response.data.length > 0) {
			localStorage.setItem("user-info", JSON.stringify(response.data[0]));
			alert("Login Successful!");
			this.$router.push({ name: 'home' });
		  }
		} catch (error) {
		  console.error(error);
		}
	  }
	}
  }
  </script>
  
  <style>
  .login-container {
	max-width: 400px;
	margin: 0 auto;
	padding: 40px;
	border-radius: 4px;
	background-color: #f7f7f7;
  }
  
  .login-heading {
	text-align: center;
	font-size: 24px;
	color: #333;
	margin-bottom: 30px;
  }
  
  form {
	display: flex;
	flex-direction: column;
  }
  
  .form-group {
	margin-bottom: 20px;
  }
  
  .form-label {
	font-weight: bold;
	margin-bottom: 5px;
	color: #333;
  }
  
  .form-input {
	padding: 10px;
	border: 1px solid #ccc;
	border-radius: 4px;
  }
  
  .login-button {
	background-color: #333;
	color: #fff;
	border: none;
	padding: 10px 20px;
	border-radius: 4px;
	cursor: pointer;
  }
  
  .login-button:hover {
	background-color: #555;
  }
  
  .signup-link {
	margin-top: 20px;
	text-align: center;
	color: #333;
  }
  
  .signup-link-text {
	color: #333;
	text-decoration: underline;
	cursor: pointer;
  }
  </style>
  