<template>
  <div class="container">
    <player-header
      v-bind:count="filteredList.length"
      v-bind:showAllStar="showAllStar"
      v-bind:sortOrder="sortOrder"
      v-on:showAllStarChanged="showAllStar=!showAllStar"
      v-on:sortOrderChanged="sortOrderChanged">
    </player-header>
    <div class="list">
      <player
        v-for="player in filteredList"
        v-bind:player="player"
        v-bind:key="player.id">
      </player>
    </div>
  </div>
</template>

<script>
import playerHeader from './player-header.vue';
import player from './player.vue';

export default {
  name: 'PlayerList',
  props: ['players'],
  components: {
    'player-header': playerHeader,
    'player': player
  },
  data: function(){
    return {
      showAllStar: false,
      sortOrder: 1
    }
  },
  methods: {
    sortOrderChanged: function(order){
      this.sortOrder = order;
    }
  },
  computed: {
    filteredList: function(){
      var newList = [];
      for(var i=0; i<this.players.length; i++){
        var isShow = true;
        if(this.showAllStar && !this.players[i].past){
          isShow = false;
        }
        if(isShow){
          newList.push(this.players[i]);
        }
      }

      if(this.sortOrder == 2){
        newList.sort(function(a,b){
          return a.height-b.height;
        });
      }else if(this.sortOrder == 3){
        newList.sort(function(a,b){
          return a.weight-b.weight;
        });
      }

      return newList;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
    width: 960px;
    margin: 0 auto;
}

.list{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.list::after{
    content: "";
    display: block;
    width: 250px;
}
</style>