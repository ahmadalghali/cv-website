<template>
  <div id="bio" class="container bio">
    <div class="row">
      <div class="col-1"></div>

      <div class="col-10 text-center hover-zoom bg-image">
        <img
          src="@/assets/ahmad-alghali.jpg"
          class="my-photo rounded-circle img-fluid mx-auto mt-5 view overlay zoom shadow-lg hover-shadow"
          alt="Photo of me"
        />
      </div>

      <div class="col-1 align-self-center">
        <a href="https://github.com/ahmadalghali" target="_blank"
          ><img src="@/assets/github.svg" class="socials"
        /></a>
        <br />
        <h5>GitHub</h5>

        <br /><br />
        <a
          href="https://www.linkedin.com/in/ahmad-alghali-2689a8147"
          target="_blank"
          ><img src="@/assets/linkedin.png" class="socials"
        /></a>
        <br />
        <h5>Linkedin</h5>
      </div>
    </div>

    <h1 class="display-5 text-center mt-5">
      Hello, I am Ahmad, a backend developer.
    </h1>
  </div>
</template>

<script>
export default { name: "Bio" };
</script>

<style scoped>
.my-photo {
  width: 400px;
}

.socials {
  width: 70px;
  cursor: pointer;
}

.socials:hover {
}
</style>