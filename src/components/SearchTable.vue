<template>
  <div class="search-table-box">
    <h1>{{searchTitle}} {{searchResults.length}}</h1>
    <div class="search-buttons">
        <li class="undo-button"><a href="#">Undo</a></li>
        <li class="clear-button"><a href="#">Clear</a></li>
    </div>
    <table>
      <tr>
        <th v-for="tableHeader in searchTableHeaders">{{tableHeader}}</th>
      </tr>
      <tr v-for="searchResult in searchResults">
        <td v-for="resultValue in searchResult">{{resultValue}}</td>
      </tr>
    </table>
   </div>
</template>

<script>
  export default {
      data() {
        return {
          searchTitle: "Search Results: Total ",
          searchTableHeaders: ["Rate", "F", "Source", "Age", "Avail", "Truck", "Truck-O", "DH-O", "F/P", "Origin", "Trip", "Destination", "DH_D", "Truck-D", "Length", "Weight", "Company", "Phone"],
          searchResults: [
            {rate: 3150, f: "Yes", source: "DAT", age: "00:01", avail: "11/24", truck: "V", truck_o: "Belwood, IL", dh_o: 371, f_p: "F", origin: "Erie, PA", trip: 422, destination: "Sealy, TX", dh_d: "", truck_d: "", length: "53 ft", weight: "43 klbs", company: "Cooyote Logistics", phon: "(773) 7992118"},
            {rate: "", f: "No", source: "DAT", age: "00:02", avail: "11/25", truck: "V", truck_o: "Belwood, IL", dh_o: 372, f_p: "F", origin: "St Clair, MI", trip: 423, destination: "Orlando, FI", dh_d: "", truck_d: "", length: "41 ft", weight: "17 klbs", company: "R & R Express", phon: "(412) 4442472"}
          ]
        }
      }
  }
</script>

<style scoped>
  .search-table-box {
    margin-top: 50px;
  }
  h1 {
    float: left;
    margin: 0;
  }
  .search-buttons {
    float: right;
    overflow: hidden;
  }
  .undo-button {
    background: url("../assets/redo.png") left no-repeat;
  }
  .clear-button {
    background: url("../assets/clear.png") left no-repeat;
  }
  table {
    clear: both;
  }
</style>