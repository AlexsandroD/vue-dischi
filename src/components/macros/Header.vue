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
    header{
        height: 80PX;
        .logo{
            height: 100%;
            background-color: #29313A;
            display: flex;
            align-items: center;
            padding: 5px;
            img{
                width: 50px;
                margin-left: 15px;

                }
        }
    }
</style>