<template>

<div class="flex-container">
  
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
       <signin />

    </sideBar>

</div>

</template>

<script>
import Signin from '../components/Signin.vue'
export default {
  name: "index",
  components:  {Signin}
}
</script>

<style scoped>
.flex-container{
  display: flex;
  
}

.flex-sidebar{
  display: flex;
  
}

p{
  margin: 1em 0;
  margin-top: 1em;
  margin-right: 0px;
  margin-bottom: 1em;
  margin-left: 0px;
}

</style>

