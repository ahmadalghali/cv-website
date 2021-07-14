<template>
  <div id="skills" class="container skills">
    <h1>Skills</h1>
    <hr />
    <br />
    <br />
    <ul>
      <div class="row ms-5">
        <div class="col-sm-12 col-md-6 col-lg-4">
          <li><img src="../assets/java.webp" alt="" /> &nbsp; Java</li>

          <!-- <li><img src="../assets/postman.jpeg" alt="" />&nbsp; Postman</li> -->
          <li><img src="../assets/git.png" alt="" /> &nbsp; Git</li>
          <li>
            <img src="../assets/android.png" alt="" />&nbsp; Android Development
          </li>
          <li><img src="../assets/agile.png" alt="" />&nbsp; Agile Scrum</li>
        </div>
        <div class="col-sm-12 col-md-6 col-lg-4">
          <li>
            <img src="../assets/spring-boot-logo.png" alt="" /> &nbsp; Spring
            Boot
          </li>
          <li><img src="../assets/js.png" alt="" /> &nbsp; JavaScript</li>
          <li><img src="../assets/github.svg" alt="" />&nbsp; GitHub</li>
          <li><img src="../assets/bootstrap.svg" alt="" />&nbsp; Bootstrap</li>
        </div>
        <div class="col-sm-12 col-md-6 col-lg-4">
          <li><img src="../assets/sql.png" alt="" /> &nbsp; SQL</li>
          <li><img src="../assets/vue.png" alt="" /> &nbsp; Vue.js</li>

          <li><img src="../assets/csharp.png" alt="" />&nbsp; C#</li>
        </div>
      </div>

      <!-- <div class="row">
        <div class="col-sm-12 col-md-6 col-lg-4">
          <li><img src="../assets/java.webp" alt="" /> &nbsp; Java</li>
          <li>
            <img src="../assets/spring-boot-logo.png" alt="" /> &nbsp; Spring
            Boot
          </li>
          <li><img src="../assets/postman.jpeg" alt="" />&nbsp; Postman</li>
          <li><img src="../assets/sql.png" alt="" /> &nbsp; SQL</li>
        </div>
        <div class="col-sm-12 col-md-6 col-lg-4">
          <li><img src="../assets/js.png" alt="" /> &nbsp; JavaScript</li>
          <li><img src="../assets/vue.png" alt="" /> &nbsp; Vue.js</li>
          <li><img src="../assets/git.png" alt="" /> &nbsp; Git</li>

          <li><img src="../assets/github.svg" alt="" />&nbsp; GitHub</li>
        </div>
        <div class="col-sm-12 col-md-6 col-lg-4">
          <li>
            <img src="../assets/android.png" alt="" />&nbsp; Android Development
          </li>
          <li><img src="../assets/csharp.png" alt="" />&nbsp; C#</li>
          <li><img src="../assets/agile.png" alt="" />&nbsp; Agile Scrum</li>
        </div>
      </div> -->
    </ul>
  </div>
</template>

<script>
export default {
  name: "Skills",
};
</script>

<style scoped>
ul li {
  list-style-type: none;

  font-size: 25px;

  margin-bottom: 50px;
}

li {
  font-size: larger;
}

.skills img {
  width: 50px;
}
</style>