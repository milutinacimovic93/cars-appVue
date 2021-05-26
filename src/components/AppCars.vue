<template>
  <div>
    <ul v-for="car in cars" :key="car.id">
      <b>Brand:</b> {{car.brand}} 
      <b>Model:</b> {{car.model}} 
      <b>Manufactory year:</b> {{car.yearOfCar}} 
      <b>Max speed:</b> {{car.maxSpeed}} 
      <b>Automatic:</b> {{car.isAutomatic}}
      <b>Engine:</b> {{car.engine}}
    </ul>
  </div>
</template>

<script>
import CarService from "../service/CarService.js";
export default {
  data() {
    return {
      cars: [],
    };
  },
  async created() {
    this.cars = await CarService.getAll();
    console.log(this.cars);
  },
};
</script>

<style>

</style>