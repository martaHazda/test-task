<template>
  <div class="main">
    <h1 class="main-header">Post trucks</h1>
    <div class="control-buttons">
      <ul>
        <li class="play-button"><a href="#"></a></li>
        <li class="new-button"><a href="#" v-on:click="openForm">New</a></li>
        <li class="delete-button"><a href="#" v-on:click="deleteAllTruckData">Delete all</a></li>
        <li class="repost-button"><a href="#">Repost all</a></li>
      </ul> 
    </div>
    <TruckForm v-if="isFormOpen" @submittedNewTruck="newTruckFrom" @closeTruckForm="hideTruckForm"/>
    <div>
      <table>
        <tr>
          <th v-for="tableHeader in tableHeaders">{{tableHeader}}</th>
        </tr>
        <tr v-for="trackTable in trackTableList">
          <td v-for="track in trackTable">{{track}}</td>
        </tr>
      </table>
    </div>
    <div>
    <SearchTable />
    </div>
  </div>
</template>

<script scoped>
import SearchTable from './SearchTable.vue';
import TruckForm from './TruckForm.vue'
export default {
  components: {
    SearchTable,
    TruckForm
  },
  name: 'HelloWorld',
  data() {
    return {
      isFormOpen: false,
      tableHeaders: ["call control", "read", "sound/auto call", "truck", "origin", "destination", "pickup", "dh-o", "dh-d", "f/p", "length", "weight", "trip", "alarm", "action"],
      trackTableList: []
    }
  },
  methods: {
    openForm(){
      this.isFormOpen = true;
    },
    newTruckFrom(newTrack){
      this.trackTableList.push(newTrack);
      console.log(this.trackTableList)
    },
    hideTruckForm(formCloseStatus){
      console.log(formCloseStatus)
      this.isFormOpen = formCloseStatus;
    },
    deleteAllTruckData() {
      this.trackTableList.splice(0, this.trackTableList.length);
    }
  }

}
</script>

<style>
  .main {
    font-family: Arial, Helvetica, sans-serif;
  }
  h1 {
    font-size: 36px;
    font-weight: normal;
    color: #516375;
    text-transform: capitalize;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
    padding: 13px 17px 13px 0;
  }
  a {
    color: #516375;
    text-decoration: none;
    font-size: 18px;
    padding-left: 50px;
  }
  .play-button {
    background: url("../assets/play.png") left no-repeat;
    border-right: 2px solid #403d3e;
  }
  .new-button {
    background: url("../assets/new.png") left no-repeat;
  }
  .delete-button {
    background: url("../assets/delete.png") left no-repeat;
  }
  .repost-button {
    background: url("../assets/repost.png") left no-repeat;
  }
  table {
    width: 100%;
  }
  table, th {
    border: 1px solid #d0cecd;
  }
  th {
    padding: 22px 30px 22px 13px;
    background-color: #454345;
    color: #fff;
    text-transform: capitalize;
    font-size: 12px;
  }
  td {
    padding: 22px 30px 22px 13px;
    background-color: #fff;
    color: #454345;
    text-align: center;
  }
</style>
