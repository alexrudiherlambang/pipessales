<template>
<div>

    <Header />

    <Nuxt />

<div class="mt-5 mb-5">
  <b-container fluid="md" class="mt-2 mb-5">
    <b-row>
      <b-col md="12">
        <b-card class="shadow-md border-0 rounded-lg">
        <div class="row justify-content-md-center">
            <div class="col-md-6">
            <div class="card">
                <div class="card-header">Login</div>
                <div class="card-body">
                <form>
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
    .card-header{
      font-size: 30px;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      font-weight: bold;
    }
</style>