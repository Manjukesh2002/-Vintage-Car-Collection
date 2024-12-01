<template>
    <div class="car-container">
        <div class="car-image">
            <img :src=car.car_image alt=car.car_model class="image"/>
        </div>
         <div>
            <h3>{{car.car_model.toUpperCase()}}</h3>
            <div class="car-details">
                <p>{{car.car_manufacturer}}</p>
                <p>{{car.color}}</p>
            </div>
            <hr/>
            <div class="car-details">
                <p><img src="https://img.icons8.com/?size=20&id=85102&format=png&color=000000"/> {{car.manufactured_year}}</p>
                <p><img src="https://img.icons8.com/?size=20&id=RAETGA6V08YU&format=png&color=000000" alt="Car mileage icon"/> {{car.mileage}}</p>
                <p><img :src="getTransmissionType(car.transmission)" alt="Car transmission type icon"/> {{car.transmission}}</p>
                <p><img src="https://img.icons8.com/?size=20&id=hc3E74U0p308&format=png&color=000000"/> {{car.engine_type}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        name:"SingleCar",
        props:{
            car:Object
        },
        methods:{
            getTransmissionType(transmission){
                if(transmission === 'Automatic') return "https://img.icons8.com/?size=20&id=53qKQtzZJZeB&format=png&color=000000";
                else return "https://img.icons8.com/?size=20&id=MAOS9vYtSK7F&format=png&color=000000";
            }
        }
    }
</script>

<style>
    .car-container{
        width:70%;
        margin:auto;
        border:transparent;
        border-radius: 10px;
        box-shadow:0 4px 8px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
        padding:1em;
        margin-bottom: 1em;
    }
    .car-image img{
        width:100%;
        height:250px;
    }
    .car-details{
        display: flex;
        justify-content:space-between;
        align-items:center;
    }
    .car-details img{
        vertical-align:middle;
    }
</style>