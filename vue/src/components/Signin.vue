<template>

     
        <div class="shadow-box">
                      <form  @submit.prevent="login">
                      <center><h3 class="title--small title--border-bottom"> <b>Sign In</b></h3></center>
                      <div
                        class="alert-danger"
                        role="alert"
                        v-if="invalidCredentials"
                          >The email address and password entered do not match any in our system. Please try again.</div><br>
                          <div
                            class="alert alert-success"
                            role="alert"
                            v-if="this.$route.query.registration"
                            >Thank you for registering, please sign in.</div>
                            <label for="username" class="sr-only">Email</label>
                            <input
                              type="text"
                              id="username"
                              class="form-control"
                              placeholder="Email"
                              v-model="user.username"
                              required
                              autofocus
                            /><br>
                            <label for="password" class="sr-only">Password</label>
                            <input
                              type="password"
                              id="password"
                              class="form-control"
                              placeholder="Password"
                              v-model="user.password"
                              required
                            /><br><br>
                            <center><button type="submit">Sign in</button></center><br>
                            <router-link :to="{ name: 'register' }">Need an account?</router-link>
                        </form>
                      </div>        
  

</template>

<script>
import authService from "../services/AuthService";

export default {
  name: "login",
  components: {},
  data() {
    return {
      user: {
        username: "",
        password: ""
      },
      invalidCredentials: false
    };
  },
  methods: {
    login() {
      authService
        .login(this.user)
        .then(response => {
          if (response.status == 200) {
            this.$store.commit("SET_AUTH_TOKEN", response.data.token);
            this.$store.commit("SET_USER", response.data.user);
            this.$router.push("/");
          }
        })
        .catch(error => {
          const response = error.response;

          if (response.status === 401) {
            this.invalidCredentials = true;
          }
        });
    }
  }
};
</script>

<style scoped>

.title--small{
  font-size: 16px;
  text-align: left;
}
.title--border-bottom {
	border-bottom: 1px solid #dbdbdb;
	padding-bottom: 4px;
  width: 90%;
  margin-top: 8px;
 
}

.form__label {
	display: block;
	font-weight: 700;
	font-size: 12px;
	margin: 6px 0 4px;
}
.sr-only{
  margin-left: 10px;
}
.form-control{
  margin-left: 10px;
}
input:placeholder-shown {
   font-style: italic;
}
</style>

