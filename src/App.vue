<template>
  <div id="app">
    
    <my-header></my-header>
    <div class="container">
      <div class="row mt-5">
        <div class="col-4">
          <my-card :articles="articles"></my-card>
        </div>
        <div class="col-4">
          <my-card></my-card>
        </div>
        <div class="col-4">
          <my-card></my-card>
        </div>
      </div>
    </div>
    
    <my-footer></my-footer>
  </div>
  
</template>

<script >
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Card from './components/Card.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    'my-header' : Header,
    'my-footer' : Footer,
    'my-card' : Card,
  },
  data(){
    return{
       articles: {title : "article1", lien : null, height : null, width : null},
    }
  },
  mounted(){
    axios
    .get('https://api.thecatapi.com/v1/images/search')
    .then(response => {
      console.log(response)
      this.articles.lien = response.data[0].url
      this.articles.title = response.data[0].id
      this.articles.height = response.data[0].height
      this.articles.width = response.data[0].width
    })
  }

}
</script>

<style lang="" >

</style>
