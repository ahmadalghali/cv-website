<template>
  <div class="container-fluid hobbies">
    <h1>Hobbies</h1>
    <br />
    <br />
    <br />

    <div class="row">
      <div class="col-sm-12 col-md-4">
        <img
          src="../assets/fishing.jpg"
          class="my-photo rounded img-fluid pb-4 mx-auto"
          alt="4.5KG Bass caught in Brighton"
        />
      </div>
      <div class="col-sm-12 col-md-4 text-center">
        <ul>
          <div class="row">
            <div class="col-sm-6 col-md-10">
              <li><b>Fishing</b></li>
              <br />
              <li><b>Basketball</b></li>
            </div>
            <div class="col-sm-6 col-md-10">
              <br />

              <li><b>Flying Drones</b></li>
              <br />
              <li><b>Wild Camping</b></li>
            </div>
          </div>
        </ul>
      </div>
      <div class="col-sm-12 col-md-4">
        <img
          src="@/assets/hiking.jpg"
          class="my-photo rounded img-fluid pb-4 mx-auto"
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