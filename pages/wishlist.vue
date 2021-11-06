<template>
<div>

    <Header />
    <Nuxt />

<div class="mt-5 mb-5">
<img src="123.png" style="display:block; margin-left:auto; margin-right:auto">
  <b-container fluid="md" class="mt-2 mb-5">
    <b-row>
      <b-col md="12">
        <b-card class="shadow-md border-0 rounded-lg">
          <h5 class="h5">Wishlist</h5>
          <hr>
          <h6 style="font-weight:bold">Connecting you with a sustainable approach</h6>
          <a>Both Buyers and Sellers benefit from Pipesales’ sustainable approach. Sellers can unlock capital by turning excess tubular products into revenue whilst removing storage and maintenance costs linked to holding surplus stock. By utilising ready-made tubular products, buyers can reduce their carbon footprint associated with new tubular production.</a><br><br>
          <h6 style="font-weight:bold">Just-in-time supply</h6>
          <a>Pipesales marketplace removes the friction of buying and selling tubular products. We help organisations target zero inventory through fast access to stock and offloading excess inventory.</a><br><br>
          <h6 style="font-weight:bold">A globally supported network</h6>
          <a>Pipesales order fulfilment is backed by Marubeni-Itochu Steel Inc (MISI). MISI has group offices and subsidiaries (92) located in North America, South America, Europe, the Middle East and Asia/Oceania. MISI's global tubular products subsidiaries utilise Total Tubular Management (TTM) as an integrated management service and provide inventory processing, inspection and maintenance functions alleviating customers from time-consuming administration tasks and supply chain risk.</a><br><br>
          <h6 style="font-weight:bold">Safe Transactions</h6>
          <a>Pipesales connects buyers and sellers with a local MISI tubular subsidiary, and transactions are processed locally, guaranteeing peace of mind.</a><br><br>     </b-card>
      </b-col>
    </b-row>
  </b-container>
</div>
</div>
</template>

<script>
  export default {

    data() {
      return {
        //header table  
        fields: ['No', 'Product Type', 'Grade', 'Size', 'Conection', 'Action'],
        //posts data
        posts: [],
      }
    },

    mounted() {
      
      //fething ke Rest API 
      this.$axios.get('/api/posts')
        .then(response => {
          
          //assign response ke state "posts"
          this.posts = response.data.data

        })
        .catch(error => {
          console.log(error.response.data)
        })
    }

  }
  
</script>

<style>
    body{
      background-color: lightgray;
    }
    .mt-5 {
      margin-top: 90px!important;
    }
    .right{
      font-weight: bold ;
      font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    }
    .left{
      font-style: oblique;
      font-size: smaller ;
    }
    .h6{
      font-style: italic;
    }
    .option_button{
      margin-top: 10px;
      margin-bottom: 10px;
      margin-right: 100px;
      margin-left: 100px;
      display: flex;
      justify-content: space-between;
      cursor: pointer;
    }
    .ob{
      margin-top: 30px;
      margin-bottom: 30px;
      margin-right: 45px;
      margin-left: 45px;
      font-size: 15px;
      border-bottom: 100px;
      font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    .h5{
      font-size: 30px;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      font-weight: bold;
    }
</style>