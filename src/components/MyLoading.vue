

<template>

<!--SEZIONE BONUS CHE APPARE FINO AL CARICAMENTO COMPLETO DEGLI ELEMENTI-->

  <div class="loading">
      Loading...
  </div>
</template>

<script>
export default {
    name: "MyLoading",
}
</script>

<style scoped lang="scss">

  .loading {
    font-size: 35px;
    color: white;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

</style>