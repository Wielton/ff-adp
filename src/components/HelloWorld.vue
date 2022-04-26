<template>
  <v-main>

    <button @click="getData">Get Data</button>
    <!-- <v-list>
      <v-list-item v-for="player in playersList"
      :key="player">
          {{player}}
      </v-list-item>
    </v-list> -->
  </v-main>
</template>

<script>
import axios from 'axios';
  export default {
    name: 'HelloWorld',
  
    data: () => ({
      playersList: []
    }),
    methods: {
      getData(event){
        console.log(event);
        axios.request({
          url: "https://api.fantasynerds.com/v1/nfl/adp?apikey=TEST",
          method: "GET",
          headers: {
            "Content-Type": "application/json",
            
          },
          
        }).then((response) =>{
          console.log(response);
        }).catch((error) =>{
          console.log(error);
        })
      }
    }
  }
</script>
