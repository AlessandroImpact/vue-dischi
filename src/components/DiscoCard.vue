<template>

<div class="d-flex flex-column text-center">
    
      <div class="box p-3">
          <div class="image">
               <img class="img-fluid" :src="details.poster">
          </div>

          <div class="title">
           <h2 class="text-center text-uppercase text-light">{{details.title}}</h2>
       </div>
        
        <div class="author">
            <span>{{details.author}}</span>
        </div>
        
        <div class="year">
            <span>{{details.year}}</span>
        </div>
        
      </div>
    </div>
  
</template>

<script>
export default {
    name:'DiscoCard'

}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
</style>