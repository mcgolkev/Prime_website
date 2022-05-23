<template>

     
        <div class="shadow-box">
               <center><h3 class="title--small title--border-bottom"> <b>Rental Application</b></h3></center>
                 
                <p>Interested in one of our properties?</p>
                 
                       <router-link style="margin-left: 10px;" :to="{ name: 'register' }">Apply Online</router-link>        
        </div>        
  

</template>

<script>

</script>

<style scoped>

p{
    font-size: 100%;
  margin-right: 0px;
  margin-left: 10px;
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

.shadow-box {
    display: flex;
    flex-direction: column;
    background-color: #edfced;
    width: 250px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    text-align: left;
    border-radius: 5px;
    margin: 15px 5px 5px 5px;
    }
    

</style>

