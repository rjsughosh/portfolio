<template>
  <section class="contact-cover">
    <div class="section-divider">
      <div></div>
    </div>

    <div class="contact-content">
      <h2>Let's Talk?</h2>
      <h3>Have a project you need help with, need inspiration, or just wanna talk? I’m always open</h3>

      <div class="contact-button">
        <button class="primary-button">
          <a href="mailto:rjsughosh@gmail.com">Start a conversation</a>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.contact-cover {
  background: #fffbfc;
  color: #000121;
  //   2d2b2b
  //   min-height: 100vh;
  display: flex;
  flex-direction: column;
  //   justify-content: center;
  align-items: center;
  h2 {
    text-align: center;
    font-size: 2rem;
    padding: 3rem;
  }
  h3 {
    text-align: center;
    font-size: 1.5rem;
  }
}

.section-divider {
  margin-top: 5rem;
}

.contact-button {
  margin: 5rem 0 15rem 0;
}
.primary-button {
  background: #2d2b2b;
  color: #fff;
  font-size: 1.5rem;
  padding: 0.75rem 4rem;
  outline: none;
  border: none;
  border-radius: 7px;

  a {
    color: #fff;
    outline: none;
    border: none;
    text-decoration: none;
  }
}

.contact-content {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}
@media only screen and (max-width: 600px) {
  .contact-content {
    height: auto;
  }
}
</style>