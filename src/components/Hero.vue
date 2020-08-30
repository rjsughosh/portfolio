<template>
  <section class="hero-cover">
    <div class="hero-left">
      <div class="hero-text">Hi, I'm Sughosh</div>
      <div class="hero-left-title">Full-Stack Developer</div>
      <div class="hero-left-desc">Currently pursuing MS in Computer Science at ASU</div>
      <div class="yellow-bar"></div>
      <div class="profile-links">
        <a href="https://www.facebook.com/sughoshrj/" target="_blank">
          <img src="./../assets/icons/facebook.svg" />
        </a>
        <a href="mailto:rjsughosh@gmail.com" target="_blank">
          <img src="./../assets/icons/gmail.svg" />
        </a>
        <a href="https://twitter.com/rj_sughosh" target="_blank">
          <img src="./../assets/icons/twitter.svg" />
        </a>
        <a href="https://www.linkedin.com/in/rjsughosh/" target="_blank">
          <img src="./../assets/icons/linkedin.svg" />
        </a>
        <a href="https://github.com/rjsughosh" target="_blank">
          <img src="./../assets/icons/github-logo.svg" />
        </a>
      </div>
    </div>

    <div class="hero-right">
      <div class="hero-right-portrait">
        <img src="../assets/portrait.png" />
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.hero-cover {
  background: #333;
  color: #fff;
  min-height: 100vh;
  display: flex;
  .hero-left {
    width: 45%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    padding-left: 10rem;

    .hero-text {
      font-size: 7rem;
      font-family: spartan-bold;
      margin: 3rem 0;
    }
    .hero-left-title {
      font-weight: 600;
      margin-bottom: 1rem;
      font-size: 2rem;
      font-family: spartan-thin;
    }
    .hero-left-desc {
      font-family: spartan-light;
      color: #cfcfcf;
      font-size: 1.5rem;
      margin-bottom: 3rem;
    }
    .yellow-bar {
      height: 1rem;
      width: 5rem;
      background: #fcd139;
    }

    .profile-links {
      margin: 1rem 0;

      display: flex;
      align-items: center;
      a {
        margin-right: 1.5rem;
        border: 1px solid #fff;
        padding: 0.5rem;
        img {
          height: 1.5rem;
        }
      }
    }
  }
  .hero-right {
    display: flex;
    align-items: flex-end;
    .hero-right-portrait {
      img {
        height: 600px;
      }
    }
  }
}
@media only screen and (max-width: 1025px) {
  .hero-cover {
    .hero-right {
      display: none;
    }
  }
}
@media only screen and (max-width: 600px) {
  .hero-cover {
    .hero-left {
      width: 100%;
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      padding-left: 0rem;

      .hero-text {
        font-size: 4rem;
        margin: 3rem;
      }

      .hero-left-desc {
        // margin-bottom: 3rem;
        margin: 3rem;
      }
    }
    .hero-right {
      display: none;
    }
  }
}
</style>
