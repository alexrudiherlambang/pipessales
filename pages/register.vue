<template>
<div>

    <div>
      <b-navbar toggleable="lg" type="light" variant="light" class="shadow-md" fixed="top">
        

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item>
                <img src="logo1.png" height="55">
            </b-nav-item>
            <b-nav-item class="right" href="login">
                <img src="key.png" height="30"><br>Login
            </b-nav-item>
            <b-nav-item class="right" href="register">
                <img src="add.png" height="30"><br>Sign Up
            </b-nav-item>
          </b-navbar-nav>
        </b-collapse>
        <b-button pill variant="outline-secondary" href="about">About Pipessales</b-button>
        <b-navbar-nav>
            <b-nav-item></b-nav-item>
        </b-navbar-nav>
        <b-button pill variant="primary" href="sales">Sales My Pipes</b-button>
        <b-navbar-nav>
            <b-nav-item class="left" href="wishlist"><img src="love.png" height="20"><br>Wishlist</b-nav-item>
            <b-nav-item class="left" href="enquiry"><img src="cart.png" height="20"><br>My Enquiry</b-nav-item>
            <b-nav-item class="left" href="compare"><img src="scale.png" height="20"><br>Compare</b-nav-item>
          </b-navbar-nav>
      </b-navbar>
    </div>

    <Nuxt />

<div class="mt-5 mb-5">
  <b-container fluid="md" class="mt-2 mb-5">
    <b-row>
      <b-col md="12">
        <b-card class="shadow-md border-0 rounded-lg">
        <div class="row justify-content-md-center">
            <div class="row justify-content-md-center">
                <div class="card">
                    <div class="card-header">Sign Up
                    </div>
                    <div class="card-body">
                    <form>
                        <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" class="form-control" placeholder="Name..">
                        </div>
                        <div class="form-group">
                        <label for="email">Email address</label>
                        <input type="email" class="form-control" placeholder="Email..">
                        </div>
                        <div class="form-group">
                        <label for="password">Password</label>
                        <input type="password" class="form-control" placeholder="Password..">
                        </div>
                        <button type="submit" class="btn btn-primary">Submit</button>
                    </form>
                    </div>
                </div>
            </div>
        </div>
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
</style>