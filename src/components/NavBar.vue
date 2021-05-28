<template>
  <nav class="navbar sticky-top ps-4 pe-4 navbar-expand-sm navbar-dark bg-dark">
    <router-link class="navbar-brand" :to="{ name: 'Home' }"
      >Ahmad Alghali</router-link
    >

    <button
      class="navbar-toggler"
      data-bs-toggle="collapse"
      data-bs-target="#navMenu"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <!-- <button v-on:click="scrollToElement({behavior: 'smooth'})">
    Smooth scroll to first element with class of .index-50
  </button> -->

    <div class="collapse navbar-collapse" id="navMenu">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item">
          <a class="nav-link" @click="scrollTo('projects')">Projects</a>

          <!-- <router-link class="nav-link">Projects</router-link> -->
        </li>
        <li class="nav-item">
          <a class="nav-link" @click="scrollTo('resume')">Resume</a>

          <!-- <router-link class="nav-link">Resume</router-link> -->
        </li>
        <li class="nav-item">
          <!-- <router-link class="nav-link" :to="{ name: 'Contact' }"
            >Contact</router-link
          > -->
          <a class="nav-link" @click="scrollTo('contact')">Contact</a>
        </li>

        <li class="nav-item">
          <a class="nav-link" @click="scrollTo('skills')">Skills</a>
          <!-- <router-link class="nav-link" :to="{ name: 'Home', hash: '#skills' }"
            >Skills</router-link
          > -->
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import Contact from "@/views/Contact.vue";

export default {
  name: "NavBar",
  components: {
    Contact,
  },
  methods: {
    scrollTo(id) {
      document.getElementById(id).scrollIntoView({
        behavior: "smooth",
      });
    },
  },
};
</script>

<style>
.a {
  text-decoration: none;
  color: grey;
}
</style>