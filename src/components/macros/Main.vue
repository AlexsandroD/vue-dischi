<template>
  <div class="container">
      <div class="row">
         <div v-for="(card, index) in cards" :key="index" class="col-12 col-sm-6 col-lg-3">ciao</div>
      </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Main",
  data() {
    return {
      cards:null
    };
  },
  methods: {
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
  },
};
</script>

<style lang="scss" scoped></style>
