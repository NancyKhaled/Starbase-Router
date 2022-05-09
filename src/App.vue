<template>
  <div id="app">
    <!--header-->
    <nav class="navbar navbar-expand-lg">
      <div class="container">
        <a class="navbar-brand" href="#">
          <img
            src="./assets/star-wars-logo.png"
            alt="star wars logo"
            width="100"
            height="60"
            class="d-inline-block align-text-top"
          >
        </a>
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <router-link class="link" to="/data/people">Characters</router-link>
          </li>
          <li class="nav-item">
            <router-link class="link" to="/data/planets">Planets</router-link>
          </li>
        </ul>
      </div>
    </nav>
    <!--content-->
    <div class="container">
      <div class="title">
        <h2>{{ title }}</h2>
        <router-view></router-view>
      </div>
      <div class="row"></div>
    </div>
    <!--footer-->
    <div class="footer-bottom clearfix">
      <div class="container copyright">
        <p class="pb-0 mb-0">
          Copyright © 2022 | developed by
          <a href="https://nancy-khaled.netlify.app/">nancy khaled</a>, All Right
          Reserved.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      title: "starbase router"
    };
  }
};
</script>

