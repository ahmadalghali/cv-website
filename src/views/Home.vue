<template>
  <div class="container">
    <div class="row">
      <img
        src="@/assets/ahmad-alghali.jpg"
        class="my-photo rounded-circle img-fluid mx-auto mt-5"
        alt="Photo of me"
      />
    </div>

    <h1 class="display-5 text-center mt-5">
      Hello, I am Ahmad, a backend developer.
    </h1>

    <div class="container experience">
      <h2>Experience</h2>
      <br />
      <h5>
        <b><em>2018 - 2019</em></b>
      </h5>
      <br />

      <p>I worked as my first job as an assistant for a disabled person.</p>
    </div>

    <div class="container skills">
      <h2>Skills</h2>
      <br />
      <ul>
        <div class="row">
          <div class="col">
            <li>Java</li>
            <li>Spring Boot</li>
            <li>SQL</li>
            <li>JavaScript</li>
          </div>
          <div class="col">
            <li>Vue.js</li>
            <li>Git & Github</li>
            <li>Java</li>
            <li>Java</li>
          </div>
        </div>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
};
</script>
<style scoped>
.my-photo {
  width: 400px;
}

.experience {
  margin-top: 150px;
}
</style>
