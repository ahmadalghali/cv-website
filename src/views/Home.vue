<template>
  <div class="container main">
    <Bio />

    <Skills />

    <Projects />

    <WorkExperience />

    <Hobbies />

    <Contact />

    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
  </div>
</template>

<script>
import Skills from "@/components/Skills.vue";
import Hobbies from "@/components/Hobbies.vue";
import WorkExperience from "@/components/WorkExperience.vue";
import Bio from "@/components/Bio.vue";
import Projects from "@/components/Projects.vue";
import Contact from "@/components/Contact.vue";

export default {
  name: "Home",
  components: {
    Skills,
    Hobbies,
    WorkExperience,
    Bio,
    Projects,
    Contact,
  },
};
</script>
<style scoped>
.experience {
  margin-top: 150px;
}

.skills {
  margin-top: 150px;
}

.contact {
  margin-top: 200px;
}

.projects {
  margin-top: 150px;
}

.hobbies {
  margin-top: 150px;
}

ul li {
  list-style-type: none;

  font-size: 25px;

  margin-bottom: 30px;
}

li {
  font-size: larger;
}
</style>
