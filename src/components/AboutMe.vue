<template>
  <section class="about-cover">
    <div class="section-divider">
      <div></div>
    </div>
    <h2>About Me</h2>
    <div class="photos-cover">
      <div class="about-me-text">
        I'm a full stack developer currently pursuing MS in CS at ASU. I have worked as a software engineer at Moonraft innovation Labs for 2 years.
        I love travelling and I've explored almost all parts of India. I moved to arizona last year and I have already visited almost every place in arizona.
        My hobbies are cooking and soccer. I love to cook and I'm getting pretty good at it. I also love to play soccer.
        I used to go play regularly before COVID hit the world. I love to watch soccer as well, my favorite team is FC Barcelona.
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.about-cover {
  background: #fffbfc;
  min-height: 100vh;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section-divider {
  margin-top: 5rem;
}
.photos-cover {
  background: url("../assets/about.jpg");
  background-size: contain;
  height: 100%;
}
.about-me-text {
  padding: 0 20rem;
  font-size: 1.2rem;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  // opacity: 1;
  background: rgba(0, 0, 0, 0.7);
  height: 100%;
  line-height: 1.5;
}

@media only screen and (max-width: 1025px) {
  .about-me-text {
    padding: 2rem;
  }
}

@media only screen and (max-width: 600px) {
  .about-cover {
    height: auto;
  }
  .about-me-text {
    padding: 2rem;
    text-align: center;
  }
}
</style>