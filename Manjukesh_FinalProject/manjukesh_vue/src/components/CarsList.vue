<template>
    <div class="grid-container">
        <div v-for="car of carsList" :key="car.car_id">
            <SingleCar :car = car />
        </div>
    </div>
</template>

<script>
    import SingleCar from "./SingleCar.vue";

    export default{
        name:"CarsList",
        components:{
           SingleCar
        },
        props:{
            carsList: Array
        }
    }
</script>

<style scoped>
    .grid-container{
        display: grid;
        grid-template-columns: auto auto;
        gap:2em;
        width:80%;
        margin:auto;
    }
</style>