<template>
<main class="container">
  
  <mainContent>
    

      
        <p> Welcome! P R I M E Property Managment, LLC is a service-oriented property 
        management company. We strive to take the stress out of owning an investment 
        property while simultaneously providing a positive living environment for our tenants. </p>

        <p> While we are located in Tampa, P R I M E Property Management provides service 
        to Tampa and the surrounding communities.</p>

        <p> Along with residential property management, we have experienced staff that 
        specialize in all forms of commercial property management. </p>

        <p> When it comes to your management needs, don't you deserve the "P R I M E" level? </p>

  </mainContent>    
         

    <sideBar>
        <div class="shadow-box">
                      <form  @submit.prevent="login">
                      <center>Resident Sign In</center>
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
                            /><br><br>
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
    </sideBar>
</main>
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
.container {
    display: grid;

    grid-template-areas:
        "mainContent" "mainContent" "sideBar";

    grid-template-columns: 75% 25%;
    
    gap: 5px;

    height: 100vh;
    background-color:#FFFFFF;
}


p{
  margin: 1em 0;
  margin-top: 1em;
  margin-right: 0px;
  margin-bottom: 1em;
  margin-left: 0px;
}

</style>

