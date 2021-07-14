<template>
  <div id="experience" class="container experience">
    <h1>Experience</h1>
    <hr />
    <br />
    <br />

    <div class="position">
      <h4>
        <b>{{ "Freelance Fullstack Web Developer" }}</b> -
        <em class="display-6 fs-4 user-select-all"
          >londontuitionacademy.netlify.app</em
        >
      </h4>
      <h5 class="text-secondary">June 2021 - Present</h5>

      <br />

      <ul class="fs-5">
        <li>
          Building a fullstack web application for a tutoring business in London
        </li>
        <li>
          Liaising directly with client and expecting a <b>100%</b> increase in
          no. of students by January 2022
        </li>
        <li>
          Upgraded from manual booking process to fully automated student
          booking service with email confirmation
        </li>
        <li>
          Implemented a scheduling assistant and a monitored student-to-tutor
          live chat feature using WebSockets
        </li>
      </ul>
      <br />
      <p class="fs-4">
        <b>Technologies:</b> Spring Boot (Java), Vue.js, PostgreSQL, Bootstrap
      </p>
    </div>

    <!-- <div class="position">
      <h4>
        <b>Graduate in BSc Computing</b> - <em>University of Greenwich</em>
      </h4>
      <h5>
        <em>Sept 2018 - May 2021</em>
      </h5>

      <br />

      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quam
        reiciendis cum non voluptas. Iure ex mollitia impedit numquam et iusto
        cum accusamus voluptatibus voluptate? Quo explicabo distinctio at!
        Fugiat ducimus doloribus sunt officiis molestias reprehenderit provident
        illum facilis repudiandae aut sit magnam repellendus maxime, placeat
        possimus ea veritatis distinctio nesciunt velit animi. Neque veniam odit
        labore deleniti? Exercitationem voluptate recusandae nam aliquam vel
        dolorem in maiores dolor minima quia quas officiis beatae, ut,
        inventore, impedit tempore mollitia ipsa. Sint similique enim fuga
        perspiciatis, nisi placeat esse maxime nihil sapiente nulla ratione
        facere ab, autem labore quis veniam expedita minus ipsa?
        
      </p>
    </div> -->
    <!-- I worked as my first job as an assistant for a disabled person. From
        basic tasks like preparing breakfast and cleaning up to physiotherapy
        sessions, it gave me an opportunity to help out the less fortunate. -->
    <!-- <div class="position">
      <h4><b>Disabled person assistant</b></h4>
      <h5>
        <em>July 2018 - Sept 2018</em>
      </h5>

      <br />

      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Blanditiis
        officiis accusamus maiores, odit quidem, culpa sunt iusto alias tenetur
        voluptatum iste tempora temporibus? Vitae sed architecto accusamus.
        Voluptatem asperiores alias unde, dolore expedita natus dignissimos nam
        aspernatur mollitia quisquam minima, soluta commodi neque omnis aliquid,
        ad sunt. Earum iusto, atque deleniti similique odit sunt pariatur
        delectus possimus? Reiciendis ratione fuga ex, dolorem nulla
        necessitatibus amet consectetur dolores aspernatur non voluptatibus
        minima excepturi corrupti sint. Nobis quasi pariatur minus saepe
        repellendus explicabo, accusantium minima incidunt consectetur esse
        recusandae rem officia quaerat dolores sunt repellat perspiciatis magni
        deserunt voluptate ipsa eius veritatis!
      </p>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "Experience",
  data() {
    return {
      positions: [
        {
          id: "1",
          title: "",
          location: "",
          period: "",
          description: "",
        },
      ],
    };
  },
};
</script>

<style scoped>
p {
  font-size: larger;
}

.position {
  margin-bottom: 100px;
}
</style>