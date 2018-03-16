<template>
  <div class="pop-up-form">
    <div class="pop-up-content">
      <h1>{{searChTableHeader}}</h1>
      <label>call control</label>
      <input type="text" v-model="newTruck.callControl">
      <label>read</label>
      <input type="text" v-model="newTruck.read">
      <label>sound/auto call</label>
      <input type="text" v-model="newTruck.soundAutoCall">
      <label>truck</label>
      <input type="text" v-model="newTruck.truck">
      <label>origin      </label>
      <input type="text" v-model="newTruck.origin">
      <label>destination</label>
      <input type="text" v-model="newTruck.destination">
      <label>pickup</label>
      <input type="text" v-model="newTruck.pickup">
      <label>dh-o</label>
      <input type="text" v-model="newTruck.dho">
      <label>dh-d</label>
      <input type="text" v-model="newTruck.dhd">
      <label>f/p</label>
      <input type="text" v-model="newTruck.fp">
      <label>length</label>
      <input type="text" v-model="newTruck.length">
      <label>weight</label>
      <input type="text" v-model="newTruck.weight">
      <label>trip</label>
      <input type="text" v-model="newTruck.trip">
      <label>alarm</label>
      <input type="text" v-model="newTruck.alarm">
      <label>action</label>
      <input type="text" v-model="newTruck.action">
      <button v-on:click="addNewTruck">Submit</button>
      <button v-on:click="closeForm">Close</button>
    </div>
   </div>
</template>

<script>
  export default {
    props: ['inputFields'],
    data() {
      return {
        searChTableHeader: "Add new Truck",
        newTruck: {
          callControl: "Test",
          read: "Y",
          soundAutoCall: "DAT",
          truck: "V",
          origin: "Erie, PA",
          destination: "Lviv",
          pickup: "",
          dho: "",
          dhd: "",
          fp: "",
          length: "41 ft",
          weight: "17 klbs",
          trip: "423",
          alarm: "",
          action: ""
        },
        truckList: []
      }
    },
    methods: {
      addNewTruck(event){
        this.$emit('submittedNewTruck', this.newTruck);
      },
      closeForm(event) {
        this.$emit('closeTruckForm', false);
      }
    }
  }
</script>

<style scoped>
  .pop-up-form {
    position: fixed;
    z-index: 1000;
    width: 100%; 
    height: 100%;
    left: 0;
    top: 0;
    overflow: auto;
    background-color: rgba(0,0,0,0.4);
  }
  .pop-up-content {
    width: 60%;
    background: #fff;
    margin: 0 auto;
    padding: 20px;
  }
  label {
    display: block;
    float: left;
    text-transform: capitalize;
    width: 120px;
    padding-top: 10px;
  }
  input {
    display: block;
    width: 200px;
    padding: 13px;
    margin-left: 140px;
    margin-bottom: 20px;
  }
  button {
    font: Helvetica, Arial, sans-serif;
    font-size: 18px;
    border: none;
    cursor: pointer;
    width: 150px;
    padding: 13px;
    color: #fff;
    background-color: #454345;
    margin-right: 20px;
  }
</style>