<template>

<header>
    <img class="logo" src="../assets/logo_spotify.png" alt="logo spotify">
</header>
  
</template>

<script>
export default {
    name: 'MyHeader'

}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';



header {
    background-color: #1E2D3B;
    min-height: 100px;

    .logo{
        padding-top: 10px;
        height: 80px;
    }
}


</style>