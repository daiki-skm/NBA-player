<template>
  <div id="app">
    <player-list v-bind:players="players"></player-list>
  </div>
</template>

<script>
import playerList from './components/player-list.vue'

export default {
  name: 'App',
  components: {
    'player-list': playerList
  },
  data: function(){
    return {
      players: [
        {id: 1,name: 'Anthony Davis<br>uniform number: 3',image: require('./assets/01.jpg'),height: 208,weight: 115,past: true},
        {id: 2,name: 'Joel Embiid<br>uniform number: 21',image: require('./assets/02.jpg'),height: 213,weight: 127,past: true},
        {id: 3,name: 'Kawhi Lenard<br>uniform number: 2',image: require('./assets/03.jpg'),height: 201,weight: 102,past: true},
        {id: 4,name: 'Pascal Siakam<br>uniform number: 43',image: require('./assets/04.jpg'),height: 206,weight: 104,past: false},
        {id: 5,name: 'Luka Doncic<br>uniform number: 77',image: require('./assets/05.jpg'),height: 201,weight: 104,past: false},
        {id: 6,name: 'Kemba Hudley Walker<br>uniform number: 8',image: require('./assets/06.jpg'),height: 183,weight: 83,past: true},
        {id: 7,name: 'James Harden<br>uniform number: 13',image: require('./assets/07.jpg'),height: 196,weight: 100,past: true},
        {id: 8,name: 'Trae Young<br>uniform number: 11',image: require('./assets/08.jpg'),height: 185,weight: 82,past: false},
        {id: 9,name: 'LeBron James<br>uniform number: 23',image: require('./assets/09.jpg'),height: 206,weight: 113,past: true},
        {id: 10,name: 'Giannis Antetokounmpo<br>uniform number: 34',image: require('./assets/10.jpg'),height: 211,weight: 110,past: true},
      ]
    }
  }
}
</script>

<style>
body{
    background: #000;
    color: #fff;
}
</style>