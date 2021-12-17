<template>
<div>
  <Select @selection="selectGenre"/>
  <div class="container" >
        <div class='cards-style' v-for="(card, index) in selectGenre" :key="index">
          <Card :info="card"/>
        </div>
  </div>
</div>
</template>

<script>
import axios from "axios";
import Card from"../commons/Card.vue";
import Select from"../sections/Select.vue"
export default {
  name: "Main",
  components:{
    Card,
    Select
  },
  data() {
    return {
      cards:null,
      genreSelection:"",
    };
  },

  computed:{
    selectGenre(){
      const arraySelected =  this.cards.filter((elm) => {
        console.log('ciao');
        return elm.genre.toLowerCase().includes(this.genreSelection.toLowerCase())
      });
      return arraySelected;
    }
  },
  
  

  


  methods: {
      
    },
    created() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((response) => {
          // handle success
         this.cards = response.data.response;
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        });
    },
};
</script>
<style lang="scss" scoped>
  .container{
    display: flex;
    width: 70%;
    margin:60px auto;
    flex-wrap: wrap;

    .cards-style{
      width:calc(100% / 10 * 2);
    }

  }   
</style>
