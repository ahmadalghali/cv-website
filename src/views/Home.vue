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
      <h2>Work Experience</h2>
      <br />
      <br />
      <br />

      <h5>
        <em>July 2018 - Sept 2018</em>
      </h5>
      <br />

      <p>
        I worked as my first job as an assistant for a disabled person. From
        basic tasks like preparing breakfast and cleaning up to physiotherapy
        sessions, it gave me an opportunity to help out the less fortunate.
      </p>
    </div>

    <div class="container skills">
      <h1>Skills</h1>
      <br />
      <br />
      <br />
      <ul>
        <div class="row">
          <div class="col">
            <li><img src="../assets/java.webp" alt="" /> &nbsp; Java</li>
            <li>
              <img src="../assets/spring-boot-logo.png" alt="" /> &nbsp; Spring
              Boot
            </li>
            <li><img src="../assets/sql.png" alt="" /> &nbsp; SQL</li>
            <li><img src="../assets/js.png" alt="" /> &nbsp; JavaScript</li>
            <li><img src="../assets/vue.png" alt="" /> &nbsp; Vue.js</li>
            <li><img src="../assets/postman.jpeg" alt="" />&nbsp; Postman</li>
          </div>
          <div class="col">
            <li><img src="../assets/git.png" alt="" /> &nbsp; Git</li>
            <li><img src="../assets/github.svg" alt="" />&nbsp; GitHub</li>
            <li>
              <img src="../assets/android.png" alt="" />&nbsp; Android
              Development
            </li>
            <li><img src="../assets/csharp.png" alt="" />&nbsp; C#</li>
            <li><img src="../assets/agile.png" alt="" />&nbsp; Agile Scrum</li>
          </div>
        </div>
      </ul>
    </div>

    <div class="container hobbies">
      <h2>Hobbies</h2>
      <br />
      <br />
      <br />

      <div class="row">
        <div class="col-4">
          <img
            src="../assets/fishing.jpg"
            class="my-photo rounded img-fluid pb-4"
            alt="4.5KG Bass caught in Brighton"
          />
        </div>
        <div class="col-4">
          <ul>
            <li>Fishing</li>
            <br />
            <li>Basketball</li>
            <br />
            <li>Flying Drones</li>
            <br />

            <li>Wild Camping</li>
          </ul>
        </div>
        <div class="col-4">
          <img
            src="@/assets/hiking.jpg"
            class="my-photo rounded img-fluid pb-4"
            alt="Climbing the summit of pen-y-fan"
          />
        </div>
      </div>
      <!-- <div class="row">
        <div class="col-6">
          <ul>
            <li>Flying Drones</li>
            <br />

            <li>Wild Camping</li>
          </ul>
        </div>
        <div class="col-6">
          <img
            src="@/assets/hiking.jpg"
            class="my-photo rounded img-fluid pb-4"
            alt="Climbing the summit of pen-y-fan"
          />
        </div>
      </div>


      <div class="row">
        <div class="col-6">
          <img
            src="../assets/fishing.jpg"
            class="my-photo rounded img-fluid pb-4"
            alt="4.5KG Bass caught in Brighton"
          />
        </div>
        <div class="col-6">
          <ul>
            <li>Fishing</li>
            <br />
            <li>Basketball</li>
            <br />
          </ul>
        </div>
      </div> -->
    </div>

    <br />
    <br />
    <br />
    <br />
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

.skills {
  margin-top: 150px;
}

.hobbies {
  margin-top: 150px;
}

ul li {
  list-style-type: none;

  font-size: 25px;

  margin-bottom: 30px;

  /* text-align: center; */
}

p {
  font-size: larger;
}

li {
  font-size: larger;
}

.skills img {
  width: 50px;
}
</style>
