<template>
  <header>
      <div class="logo"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/768px-Spotify_logo_without_text.svg.png" alt="logo spotify"></div>
  </header>
</template>

<script>
export default {
    name:'Header'
}
</script>

<style lang="scss" scoped>
    .logo{
        background-color: #29313A;
        display: flex;
        align-items: center;
        padding: 5px;
        img{
            width: 10px;
        }
    }
</style>