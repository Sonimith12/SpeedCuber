<template>
    <div class="signup-container">
      <h1 class="signup-heading">Sign Up</h1>
      <form @submit.prevent="signup" class="signup-form">
        <div class="form-group">
          <label for="username" class="form-label">Username</label>
          <input type="text" v-model="username" id="username" name="username" class="form-input" placeholder="Enter your username" required>
        </div>
        <div class="form-group">
          <label for="email" class="form-label">Email</label>
          <input type="email" v-model="email" id="email" name="email" class="form-input" placeholder="Enter your email" required>
        </div>
        <div class="form-group">
          <label for="password" class="form-label">Password</label>
          <input type="password" v-model="password" id="password" name="password" class="form-input" placeholder="Enter your password" required>
        </div>
        <button type="submit" class="signup-button">Sign Up</button>
      </form>
      <div class="login-link">
        Already have an account? <RouterLink to="/login" class="login-link-text">Login</RouterLink>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: "SignUp",
    data() {
      return {
        username: "",
        email: "",
        password: ""
      };
    },
    methods: {
      async signup() {
        try {
          const emailExists = await axios.get(`http://localhost:3000/users?email=${this.email}`);
          if (emailExists.data.length > 0) {
            alert("Email already exists. Please choose a different email.");
            return;
          }
          
          const response = await axios.post("http://localhost:3000/users", {
            name: this.username,
            email: this.email,
            password: this.password
          });
  
          console.log(response);
          console.log(response.status);
          if (response.status === 201) {
            localStorage.setItem("user-info", JSON.stringify(response.data));
            alert("Sign Up Successful!");
            this.$router.push({ name: 'login' });
          }
        } catch (error) {
          console.error(error);
        }
      }
    }
  };
  </script>
  
  <style>
  .signup-container {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f2f2f2;
    border-radius: 5px;
    box-shadow: 0px 0px 10px #999;
  }
  
  .signup-heading {
    text-align: center;
    color: #333;
  }
  
  .signup-form {
    margin-top: 20px;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  .form-label {
    display: block;
    margin-bottom: 5px;
    color: #333;
    font-weight: bold;
  }
  
  .form-input {
    width: 100%;
    padding: 10px;
    border: none;
    background-color: #f2f2f2;
    border-radius: 3px;
  }
  
  .signup-button {
    display: block;
    width: 100%;
    padding: 10px 20px;
    border: none;
    background-color: #333;
    color: #fff;
    border-radius: 3px;
    cursor: pointer;
  }
  
  .signup-button:hover {
    background-color: #555;
  }
  
  .login-link {
    margin-top: 20px;
    text-align: center;
    color: #333;
  }
  
  .login-link-text {
    color: #333;
    text-decoration: underline;
    cursor: pointer;
  }
  </style>
  