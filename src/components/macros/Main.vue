<template>
  <div class="container">
         <div class='cards-style' v-for="(card, index) in cards" :key="index">
           <Card :info="card"/>
         </div>
  </div>
</template>

<script>
import axios from "axios";
import Card from"../commons/Card.vue";
export default {
  name: "Main",
  components:{
    Card,
  },
  data() {
    return {
      cards:null
    };
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
    width: 70%;
    margin:80px auto;
    display: flex;
    flex-wrap: wrap;
    .cards-style{
      width:calc(100% / 10 * 2);
    }
  }
      
</style>
