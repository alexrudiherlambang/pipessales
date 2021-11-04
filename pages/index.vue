<template>
<div>

    <div>
      <b-navbar toggleable="lg" type="light" variant="light" class="shadow-md" fixed="top">
        <img src="logo.png">

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
<img src="1.png">
  <b-container fluid="md" class="mt-2 mb-5">
    <b-row>
      <b-col md="12">
        <b-card class="shadow-md border-0 rounded-lg">
          <h6 class="h6">I`m Looking For ...</h6>
          <b-form-select-option>
            <select>
              <option value="">Product Type</option>
            </select>
            <select>
              <option value="">Grade</option>
             </select>
            <select>
              <option value="">Size</option>
            </select>
            <select>
              <option value="">Connection</option>
            </select>
          </b-form-select-option>
          <hr>
          <h5>OUR PRODUCT</h5>
          <b-button :to="{name: 'post-create'}" variant="primary" class="mb-3">TAMBAH</b-button>
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
        fields: ['title', 'content', 'actions'],
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
    }
    .left{
      font-style: oblique;
      font-size: smaller ;
    }
    .h6{
      font-style: italic;
    }
</style>