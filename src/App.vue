<template>
  <div id="app">
    <div
      :class="[
        'g-cursor',
        { 'g-cursor_hover': hover },
        { 'g-cursor_hide': hideCursor },
      ]"
    >
      <div :style="cursorCircle" class="g-cursor__circle"></div>
      <div class="g-cursor__point" ref="point" :style="cursorPoint"></div>
    </div>
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
      xChild: 0,
      yChild: 0,
      xParent: 0,
      yParent: 0,
      hover: false,
      hideCursor: true,
    };
  },
  computed: {
    cursorCircle() {
      return `transform: translateX(${this.xParent}px) translateY(${this.yParent}px) translateZ(0) translate3d(0, 0, 0);`;
    },
    cursorPoint() {
      return `transform: translateX(${this.xChild - 3}px) translateY(${this
        .yChild - 3}px) translateZ(0) translate3d(0, 0, 0);`;
    },
  },
  methods: {
    moveCursor(e) {
      this.xChild = e.clientX;
      this.yChild = e.clientY;
      setTimeout(() => {
        this.xParent = e.clientX - 15;
        this.yParent = e.clientY - 15;
      }, 100);
    },
  },
  mounted() {
    document.addEventListener("mousemove", this.moveCursor);
    document.addEventListener("mouseleave", (e) => {
      console.log(e);
      this.hideCursor = true;
    });
    document.addEventListener("mouseenter", (e) => {
      console.log(e);
      this.hideCursor = false;
    });
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

.g-cursor {
  &_hide {
    opacity: 0;
    width: 60px;
    height: 60px;
    transition: width 0.6s ease, height 0.6s ease, opacity 0.6s ease;
    display: none;
  }

  &__circle {
    pointer-events: none;
    user-select: none;
    top: 2.5rem;
    left: 2.5rem;
    position: fixed;
    width: 25px;
    height: 25px;
    border: 2px solid #3988fd;
    border-radius: 100%;
    z-index: 5555;
    backface-visibility: hidden;
    transition: opacity 0.6s ease;
  }
}
</style>
