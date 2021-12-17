<template>
  <div>
    <Select @selection="selectGenre" />
    <div class="container">
        <Card :info="card" v-for="(card, index) in genreSelected" :key="index" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Card from "../commons/Card.vue";
import Select from "../sections/Select.vue";

export default {
  name: "Main",
  components: {
    Card,
    Select,
  },
  data() {
    return {
      cards: [],
      genreSelection: "",
    };
  },
  methods: {
    selectGenre(payload) {
      this.genreSelection = payload;
      console.log('methods')
    },
  },
  computed: {
    genreSelected() {
     return this.cards.filter((elm) => {
        return elm.genre
          .toLowerCase()
          .includes(this.genreSelection.toLowerCase()); // true o false
      }); 
    },
  },
  created() {
    console.log('created')
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        // handle success
        this.cards = response.data.response;
        console.log('axios')

      })
      .catch(function (error) {
        // handle error
        console.log(error);
      });
  },
};
</script>
<style lang="scss" scoped>
.container {
  width: 70%;
  margin: 60px auto;
  display: grid;
  justify-content: center;
  grid-template-columns:repeat(auto-fill, 200px);
  column-gap:30px;
  row-gap: 20px;
}



</style>
