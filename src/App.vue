<template>
  <div id="app">
    <div class="landing-section">
      <Header />
      <Hero />
    </div>
    <Skills />
    <Projects />
    <AboutMe />
    <Contact />

    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
import AboutMe from "./components/AboutMe.vue";
import Hero from "./components/Hero.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
export default {
  name: "App",
  components: { Header, Footer, Hero, Skills, Projects, AboutMe, Contact },
  data() {
    return {
     
    };
  },
  computed: {
    
  },
  methods: {
   
  },
  mounted() {
    
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
}

@font-face {
  font-family: ubuntu-regular;
  src: url("./assets/fonts/ubuntu/Ubuntu-R.ttf");
}
@font-face {
  font-family: ubuntu-light;
  src: url("./assets/fonts/ubuntu/Ubuntu-L.ttf");
}
@font-face {
  font-family: spartan;
  src: url("./assets/fonts/Spartan/static/Spartan-Regular.ttf");
}
@font-face {
  font-family: spartan-light;
  src: url("./assets/fonts/Spartan/static/Spartan-Light.ttf");
}
@font-face {
  font-family: spartan-thin;
  src: url("./assets/fonts/Spartan/static/Spartan-Thin.ttf");
}
@font-face {
  font-family: spartan-bold;
  src: url("./assets/fonts/Spartan/static/Spartan-Bold.ttf");
}

html {
  font-family: spartan;
  // cursor: none;
}

.landing-section {
  display: flex;
  flex-direction: column;
  height: 100vh;
}
.section-divider {
  display: flex;
  justify-content: center;
  div {
    width: 15rem;
    height: 2px;
    background: #4b4b4b;
  }
}

h2 {
  text-align: center;
  font-size: 2rem;
  padding: 3rem;
}
h3 {
  text-align: center;
  font-size: 1.5rem;
}
</style>
