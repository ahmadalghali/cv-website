<template>
  <div class="container main">
    <Bio />

    <Skills />

    <Experience />

    <Education />

    <Projects />

    <Hobbies />

    <Contact />
  </div>
</template>

<script>
import Skills from "@/components/Skills.vue";
import Hobbies from "@/components/Hobbies.vue";
import Experience from "@/components/Experience.vue";
import Bio from "@/components/Bio.vue";
import Projects from "@/components/Projects.vue";
import Contact from "@/components/Contact.vue";
import Education from "@/components/Education.vue";

export default {
  name: "Home",
  components: {
    Skills,
    Hobbies,
    Experience,
    Bio,
    Projects,
    Contact,
    Education,
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
  margin-bottom: 100px;
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
