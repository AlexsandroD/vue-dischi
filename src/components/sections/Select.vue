<template>
  <div class="select">
    <select v-model="genreSelection" @change="$emit('selection',genreSelection)">
        <option>---</option>
        <option>Rock</option>
        <option>Pop</option>
        <option>Metal</option>
        <option>Jazz</option>
    </select>
    <div class="select_arrow">
    </div>
  </div>
</template>

<script>
export default {
    name:'Select',
    data(){
        return{
             genreSelection:"",
        }
    }
}
</script>

<style lang="scss" scoped>
    .select{
    width: 100%;
    text-align: center;
    margin: 10px 0;
    select{
      padding: 5px;
      width: 10%;
      border-radius: 10px;
      color: #1ED560;
      background-color: #1E2D3B;
      border:1px solid #4e4f50;
      &:hover{
        background-color: #1E2D3B;
      }
      &:active{
      border:1px solid #4e4f50;
      }
    }
  }
</style>