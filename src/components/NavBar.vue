<template>
  <nav class="navbar sticky-top ps-4 pe-4 navbar-expand-sm navbar-dark bg-dark">
    <!-- <router-link class="navbar-brand" :to="{ name: 'Home' }"
      >Ahmad Alghali</router-link
    > -->

    <a class="navbar-brand" @click="scrollTo('bio')">Ahmad Alghali</a>

    <button
      class="navbar-toggler"
      data-bs-toggle="collapse"
      data-bs-target="#navMenu"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navMenu">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item">
          <a
            class="nav-link"
            data-bs-toggle="collapse"
            data-bs-target="#navMenu"
            @click="scrollTo('skills')"
            >Skills</a
          >
        </li>

        <li class="nav-item">
          <a
            class="nav-link"
            data-bs-toggle="collapse"
            data-bs-target="#navMenu"
            @click="scrollTo('projects')"
            >Projects</a
          >
        </li>
        <!-- <li class="nav-item">
          <a
            class="nav-link"
            data-bs-toggle="collapse"
            data-bs-target="#navMenu"
            @click="scrollTo('experience')"
            >Experience</a
          >
        </li> -->
        <li class="nav-item">
          <a
            class="nav-link"
            data-bs-toggle="collapse"
            data-bs-target="#navMenu"
            @click="scrollTo('education')"
            >Education</a
          >
        </li>
        <li class="nav-item">
          <a
            class="nav-link"
            data-bs-toggle="collapse"
            data-bs-target="#navMenu"
            @click="scrollTo('contact')"
            >Contact</a
          >
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
      let element = document.getElementById(id);
      window.scroll({
        top: element.offsetTop - 100,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: grey;
  cursor: pointer;
}
</style>