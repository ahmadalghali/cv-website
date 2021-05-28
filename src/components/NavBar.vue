<template>
  <nav class="navbar ps-4 pe-4 navbar-expand-sm navbar-dark bg-dark">
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

    <div class="collapse navbar-collapse" id="navMenu">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item">
          <!-- <router-link class="nav-link">Projects</router-link> -->
        </li>
        <li class="nav-item">
          <!-- <router-link class="nav-link">Resume</router-link> -->
        </li>
        <li class="nav-item">
          <router-link class="nav-link" :to="{ name: 'Contact' }"
            >Contact</router-link
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
};
</script>

<style>
.a {
  text-decoration: none;
  color: grey;
}
</style>