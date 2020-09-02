<template>
  <section class="about-cover">
    <div class="section-divider">
      <div></div>
    </div>
    <h2>About Me</h2>
    <div class="photos-cover">
      <div class="about-me-text">
        <p>
          I'm a full stack developer working part-time at EdPlus at ASU and I'm
          currently pursuing MS in CS at ASU. Prior to this, I worked as a
          software engineer at Moonraft innovation Labs,Bengaluru for 2 years. I
          am a graduate of RNS Institute of technology, Bengaluru, where I
          majored in Computer Science Degree. I currently live in Tempe, Az.
          When I’m not keeping busy with coding, I enjoy travelling and cooking.
          Moving around a lot inspired me to travel and explore the world around
          me. I love meeting new people and learning about the places they come
          from. I believe traveling is the best way to make new friends. I've
          travelled to almost all parts of India. I moved to Arizona last year
          and I hope to continue to keep vising new places. My other hobbies are
          cooking and soccer. I love to cook and I'm getting pretty good at it.
          Along with my friends I recently started an
          <a
            class="a-tag"
            target="_blank"
            href="https://www.instagram.com/az.adugemane/"
          >Instagram</a>
          account to share some photos of the food we cook. I also love to play
          soccer and video games. I used to play soccer regularly before COVID
          hit the world. I love to watch soccer as well, my favorite team is FC
          Barcelona.
        </p>
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
  text-align: justify;

  .a-tag {
    // text-decoration: none;
    color: inherit;
  }
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
