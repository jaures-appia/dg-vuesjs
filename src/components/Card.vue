<template>
  <div>
        <div class="card" style="width: 18rem;">
            <img :src="articles.lien" class="card-img-top" alt="image">
            <div class="card-body">
                <h5 class="card-title">{{ articles.title }}</h5>
                <p class="card-text">
                    <span>height : </span>{{ articles.height }}<br>
                    <span>width : </span>{{ articles.width }}
                </p>
                <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
        </div>
  </div>
</template>

<script>

export default {
  name: 'Card',
  data(){
      return{
         
      }
  },
  props: ["articles"],

  
}
</script>

<style lang="scss">

</style>
