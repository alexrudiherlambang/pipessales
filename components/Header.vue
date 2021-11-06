<template>
  
    <div>
      <b-navbar toggleable="lg" type="light" variant="light" class="shadow-md" fixed="top">
        

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="/">
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
</template>