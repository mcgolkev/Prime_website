<template>

     
        <div class="shadow-box">
               <center><h3 class="title--small title--border-bottom"> <b>Rental Application</b></h3></center>
                    <br>
                      <p>Interested in one of our properties?</p>
                    
                       <router-link :to="{ name: 'register' }">Apply Online</router-link>        
        </div>        
  

</template>

<script>

</script>

<style scoped>

p{
  margin: 1em 0;
  margin-top: 1em;
  margin-right: 0px;
  margin-bottom: 1em;
  margin-left: 0px;
}
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

</style>

