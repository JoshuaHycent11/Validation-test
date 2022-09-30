<template>
  <section class="reach vh-100">
<div class="container">
    <h6 class="text-center">{{ checkiing }}</h6>
    <h4> count is: {{ count }} </h4>
    <button @click="increseCount" class="btn btn-primary mb-4">count</button>
    <h5 class="text-center mb-4">{{ title }}</h5>  
    <div class="row">                            
        <div class="col-lg-3 mb-3  " v-for="team in team" :key="team">
            <div class="card text-center text-info shadow py-2">
               <h5>{{ team.name }}</h5>
            <h6>{{ team.gender }}</h6>
            <h6>{{ team.role }}</h6>
            <p>{{ team.complextion}}</p> 
            </div>
            
        </div>
    </div>
</div>
  </section>
</template>

<script>
let id = 0;
export default {
data(){
    return{
        title:'KODEHAUZ STAFFS',
        count: 0,
       checkiing:'I Am Learning More About Vue',
        team:[ 
            {
                id: id++,
                name:'Oguchukwu',
                gender:'Male',
                role:'Web Developer',
                complextion:'He is Fair in complextion'
            },
            {
                id: id++,
                name:'Victor',
                gender:'Male',
                role:'Auto Card',
                complextion:'He is Chocolate in complextion'
            },
            {
                id: id++,
                name:'Achom',
                gender:'Male',
                role:'Android Developer',
                complextion:'He is  Fair in complextion'
            },
            {
                id: id++,
                name:'Joshua',
                gender:'Male',
                role:'Web Developer',
                complextion:'He is Chocolate in complextion'
            },
            {
                id: id++,
                name:'Ehechi',
                gender:'Male',
                role:'UI/UX Designer',
                complextion:'He is Fair in complextion'
            },
            {
                id: id++,
                name:'Jacob',
                gender:'Male',
                role:'Python Developer',
                complextion:'He is Chocolate in complextion'
            },
            {
                id: id++,
                name:'Kingley',
                gender:'Male',
                role:'Android Developer',
                complextion:'He is Chocolate in complextion'
            },
            ],
    }
},
 methods: {
    increseCount() {
      this.count++;
      if (this.count === 10) {
        document.querySelector(".reach").classList.add("orange");
        document.querySelector(".reach").classList.remove("green");
      }
      else{
        document.querySelector(".reach").classList.remove("green");
      }
    },
   
  },

  
}
</script>

<style scoped>
.reach{
    padding-top: 130px;
}
 .orange{
    color: green;
  }
  .red{
    background: #ff0000;
    
  }

  .card{
    border:none;

  }
</style>