<template>
  <section class="meeting ">
    <div class="container">
      <div class="d-flex justify-content-between align-items-center mb-5">
        <div>
         <input type="text" placeholder="Search" class="search form-control">
        </div>
        
       <div>
        <select  name="Filter by name" id="" class="form-control" >
          <option value="Filter by name">Filter by Region</option>
          <option value="Filter by name">Africa</option>
          <option value="Filter by name">America</option>
          <option value="Filter by name">Asia</option>
          <option value="Filter by name">Europe</option>
          <option value="Filter by name">Oceania</option>
        </select>
       </div>
      </div>
      <div class="row">
       <div class="col-lg-3 ments" v-for="country in country" :key="country" >
          <div class="card bg-light-50 shadow">
            <div class="flaging">
            <img :src="country.flag" alt="" class="img-fluid"> 
          </div> 
            <div class="card-body">
               <h5 class="nat">{{country.name }}</h5>
               <div class="d-flex "><p class="nat mr-2">Population:</p><span>{{country.population}}</span></div> 
                <div class="d-flex"><p class="nat mr-2">Region:</p><span>{{ country.region }}</span></div>
                <div class="d-flex"><p class="nat mr-2">Capital:</p><span>{{ country.capital }}</span> </div> 
            </div>
          </div>
        </div> 
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  name: 'HomeView',
  data(){
    return{
      country:[],
    }
  },
    created(){
      axios
      .get("https://restcountries.com/v2/all")
      .then((res)=>{
        const{ data } = res;
        this.country = data
        console.log(res);
      })
  }
   
}
</script>

<style scoped>
.meeting{
  padding-top: 130px;
}

.flaging img{
  display: block;
  width: 100%;
  height: 180px;
  
}

.card{
  height: 100%;
  border: none;
}

.ments{
 margin-bottom: 27px;
}

.search{
  width: 350px;
}

.nat{
        font-weight: bold;
    }
</style>