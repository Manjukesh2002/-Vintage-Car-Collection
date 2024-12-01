<template>
  <CarHeader/>
  <CarsList :carsList = carsList />
</template>

<script>
import CarHeader from "./components/CarHeader.vue";
import CarsList from "./components/CarsList.vue";

  export default{
    name:"App",
    components:{
      CarHeader,
      CarsList
    },
    data(){
      return {
        carsList:[]
      }
    },methods:{
      async fetchCarDetails(){
        const res = await fetch("http://localhost:9143/api");
        const carsData = await res.json();
        return carsData[0].cars;
      }
    },
    async created(){
      this.carsList = await this.fetchCarDetails();
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400..700;1,400..700&display=swap');

  *{
     font-family: "Lora", serif;
  }
</style>