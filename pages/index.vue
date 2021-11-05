<template>
<div>

    <div>
      <b-navbar toggleable="lg" type="light" variant="light" class="shadow-md" fixed="top">
        <img src="logo1.png">

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item class="right">
              <img src="key.png" height="30"><br>Login</b-nav-item>
            <b-nav-item class="right"><img src="add.png" height="30"><br>Sign Up</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
        <b-button pill variant="outline-secondary">About Pipessales</b-button>
        <b-navbar-nav>
            <b-nav-item></b-nav-item>
        </b-navbar-nav>
        <b-button pill variant="primary">Sales My Pipes</b-button>
        <b-navbar-nav>
            <b-nav-item class="left"><img src="love.png" height="20"><br>Wishlist</b-nav-item>
            <b-nav-item class="left"><img src="cart.png" height="20"><br>My Enquiry</b-nav-item>
            <b-nav-item class="left"><img src="scale.png" height="20"><br>Compare</b-nav-item>
          </b-navbar-nav>
      </b-navbar>
    </div>

    <Nuxt />

<div class="mt-5 mb-5">
<img src="1.png" style="border-sizing:border-box">
  <b-container fluid="md" class="mt-2 mb-5">
    <b-row>
      <b-col md="12">
        <b-card class="shadow-md border-0 rounded-lg">
          <h6 class="h6">I`m Looking For ...</h6>
          <b-form-select-option class="option_button">
            <b-button variant="outline-warning">
              <select class="ob">
              <option value="">Product Type</option>
              </select>
            </b-button>
            <b-button variant="outline-warning">
              <select class="ob">
              <option value="">Grade</option>
              </select>
            </b-button><b-button variant="outline-warning">
              <select class="ob">
              <option value="">Size</option>
              </select>
            </b-button><b-button variant="outline-warning">
              <select class="ob">
              <option value="">Connection</option>
              </select>
            </b-button>
            <b-button variant="success">Find !!!</b-button>
          </b-form-select-option>
          <hr>
          <h5>OUR PRODUCT</h5>
          <b-table striped bordered hover :items="items" :fields="fields" show-empty></b-table>
        </b-card>
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
        fields: ['No', 'Product Type', 'Grade', 'Size', 'Connectiion', 'Action'],
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
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
</style>