<template>
  <div class="container hobbies">
    <h1>Hobbies</h1>
    <hr />
    <br />
    <br />

    <div class="row">
      <div class="col-sm-12 col-md-4">
        <img
          src="../assets/fishing.jpg"
          class="my-photo rounded img-fluid mx-auto shadow-lg"
          alt="4.5KG Bass caught in Brighton"
        />
      </div>
      <div class="col-sm-12 col-md-4 text-center align-self-center">
        <ul>
          <div class="row">
            <div class="col">
              <li><b class="display-6">Fishing</b></li>
              <br />
              <li><b class="display-6">Basketball</b></li>
              <br />

              <li><b class="display-6">Drone Videography</b></li>
              <br />
              <li><b class="display-6">Wild Camping</b></li>
            </div>
          </div>
        </ul>
      </div>
      <div class="col-sm-12 col-md-4">
        <img
          src="@/assets/hiking.jpg"
          class="my-photo rounded img-fluid mx-auto shadow-lg"
          alt="Climbing the summit of pen-y-fan"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hobbies",
};
</script>

<style scoped>
ul li {
  list-style-type: none;

  font-size: 25px;

  margin-bottom: 30px;
}

li {
  font-size: larger;
}
</style>