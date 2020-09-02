<template>
  <section class="projects-cover">
    <div class="section-divider">
      <div></div>
    </div>
    <h2>My Work</h2>
    <h3>Here are a few projects I've worked on recently. Want to see more? Email me.</h3>

    <div class="projects-wrap">
      <div
        v-on:click="flip(project.id)"
        class="container"
        v-for="project in projects"
        :key="project.id"
      >
        <div v-bind:class="{flipped: project.status}" class="card">
          <div
            @mouseenter="project.hover = true"
            @mouseleave="project.hover = false"
            v-bind:class="{transparentFront: project.status}"
            class="front clickable"
          >
            <div class="project-bottom">
              <div class="project-title">
                <div class="project-icon">
                  <img :src="getImgUrl(project.icon)" />
                </div>
                <div class="Project-tile-text">{{project.name}}</div>
              </div>
              <!-- <div class="project-tags">{{project.tag}}</div> -->
              <div v-if="project.hover" class="project-tags">
                <span>See more</span>
                <img src="./../assets/icons/arrow.svg" />
              </div>
            </div>
          </div>
          <div class="back">
            <p>{{project.description}}</p>
            <div v-if="project.link" class="icons clickable">
              <img @click="openLink(project.link)" src="./../assets/icons/github-logo.svg" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>


<script>
export default {
  data() {
    return {
      isActive: false,
      projects: [
        {
          id: 1,
          name: "Real-time facial emotion recognition",
          icon: "python.svg",
          tag: "Python",
          description: `Implemented a real-time application that takes continuous image input from a webcam and instantly detects the facial emotion of the person 
                        and overlays a suitable emoji on the person’s face. Trained a convolutional Neural Networks using custom data set of 50 people, CK+ and JAFFE.`,
          link: "https://github.com/rjsughosh/RealtimeFacialEmotionRecognition",
          status: false,
          hover: false,
          tags: ["python", "caffe", "opencv"]
        },
        {
          id: 2,
          name: "Jazz serverless development platform",
          icon: "angular.svg",
          tag: "Angular",
          description: `Jazz, a serverless development platform, accelerates adoption of serverless technology within your enterprise. Jazz comes with a beautiful UI 
                        that lets developers quickly create serverless applications with a click of a button. Its modular design makes it easy to add new integrations 
                        that your enterprise needs.`,
          link: "https://github.com/rjsughosh/jazz",
          status: false,
          hover: false,
          tags: ["Angular", "AWS", "Serverless", "Node.js"]
        },
        {
          id: 3,
          name: "Twitter network analysis",
          icon: "python.svg",
          tag: "Python",
          description: `Developed a twitter followers network visualization graph by leveraging twitter API using tweepy in Python and performed analysis on the 
                        graph such as Degree distribution, Clustering Coefficient, Pagerank and diameter.`,
          link: "",
          status: false,
          hover: false,
          tags: ["Python", "Tweepy"]
        },
        {
          id: 4,
          name: "Meal Detection",
          icon: "python.svg",
          tag: "Python",
          description: `Developed a program in python to classify the time-series data of a person’s Continuous Glucose Monitoring (CGM) as a meal/non-meal period. 
                        Extracted statistical features like Standard deviation, Area under curve, Velocity, Fast Fourier Transform (FFT), Polynomial Fit. Achieved 
                        an accuracy of 74%.`,
          link: "",
          status: false,
          hover: false,
          tags: ["python", "sklearn"]
        },
        {
          id: 5,
          name: "Fake news classification",
          icon: "python.svg",
          tag: "Python",
          description: `Implemented an application in Python to classify fake news by comparing two news titles and predicting if these agree, disagree or are 
                        completely unrelated. Extracted features by using Universal sentence encoder and used multiple classifiers including SVM, Decision 
                        trees and Naïve Bayes with an average of 82% accuracy`,
          link: "",
          status: false,
          hover: false,
          tags: ["python", "sklearn"]
        },
        {
          id: 6,
          name: "Stocks Tracker",
          icon: "angular.svg",
          tag: "Angular",
          description: `A simple web app in Angular for adding stocks tracker and visualizing live data`,
          link: "https://github.com/rjsughosh/stocks-app",
          status: false,
          hover: false,
          tags: ["Angular"]
        },
        {
          id: 7,
          name: "Dream 11 - Make your starting X1",
          icon: "vue.svg",
          tag: "VueJS",
          description:
            " A simple web application in VueJS to create and visualize a starting 11 for your football team",
          link: "https://github.com/rjsughosh/dream-11",
          status: false,
          hover: false,
          tags: ["VueJS"]
        },
        {
          id: 8,
          name: "Bounce - OpenGL game",
          icon: "cplusplus.svg",
          tag: "C++",
          description:
            "Built a game similar to Nokia classic ‘Bounce’. C++; OpenGL.",
          link: "",
          status: false,
          hover: false,
          tags: ["C++"]
        }
      ]
    };
  },
  methods: {
    getImgUrl(img) {
      return require("../assets/icons/icons-white/" + img);
    },
    openLink(link) {
      if (link) {
        window.open(link);
      }
    },
    flipToBack(id) {
      let el = this.$refs[id];
      console.log(el[0].classList);
      // console.log(el);
      el[0].classList.add("flipped");
    },
    flip(id) {
      for (let i in this.projects) {
        if (this.projects[i].id == id) {
          console.log("name", this.projects[i].name);
          this.projects[i].status = !this.projects[i].status;
        }
      }
      // let el = this.projects.filter(x => x.id == id);
      // el.status = !el.status;
      // console.log(this.isActive);
      // this.isActive = !this.isActive;
    }
  }
};
</script>

<style scoped lang="scss">
.projects-cover {
  min-height: 100vh;
  background: #fffbfc;
  color: #000;
  h2 {
    text-align: center;
    font-size: 2rem;
    padding: 3rem;
  }
  h3 {
    text-align: center;
    font-size: 1.5rem;
  }
  .projects-wrap {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding: 3rem 10rem 3rem 10rem;
  }

  .project-bottom {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
  }
  .project-title {
    font-size: 1.5rem;
    margin: 1rem;
    display: flex;
    text-align: left;
    align-items: center;
    img {
      margin-right: 1rem;
      height: 2.5rem;
    }
  }
  .project-tags {
    // visibility: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    bottom: 0;
    text-align: center;
    margin-bottom: 1rem;
    img {
      height: 1.2rem;
      margin: 0 0.5rem;
    }
  }
}

.clickable {
  cursor: pointer;
}

@media only screen and (max-width: 1025px) {
  .projects-cover {
    .projects-wrap {
      padding: 3rem 6rem;
    }
  }
}
@media only screen and (max-width: 600px) {
  .projects-cover {
    min-height: 100vh;
    background: #fffbfc;
    color: #000;

    .projects-wrap {
      padding: 3rem 0rem 3rem 0rem;
    }
  }
}

// ---------------
.container {
  position: relative;
  -webkit-perspective: 800px;
  -moz-perspective: 800px;
  -o-perspective: 800px;
  perspective: 800px;
  width: 300px;
  height: 300px;
  color: #fff;
  border-radius: 5px;
  padding: 1rem;
  margin: 1rem;
}
.card {
  width: 100%;
  height: 100%;
  position: absolute;
  -webkit-transition: -webkit-transform 0.7s;
  -moz-transition: -moz-transform 0.7s;
  -o-transition: -o-transform 0.7s;
  transition: transform 0.7s;
  -webkit-transform-style: preserve-3d;
  -moz-transform-style: preserve-3d;
  -o-transform-style: preserve-3d;
  transform-style: preserve-3d;
  transform-origin: 50% 50%;
  -webkit-transform-origin: 50% 50%;
}
.card .front,
.card .back {
  display: block;
  height: 100%;
  width: 100%;
  color: white;
  text-align: center;
  position: absolute;
  backface-visibility: hidden;
}
.card .front {
  border-radius: 5px;
  background: #2d2b2b;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  backface-visibility: hidden;
  opacity: 1;
  transition: 0.7s opacity;
}
.card .back {
  -webkit-transform: rotateY(180deg);
  -moz-transform: rotateY(180deg);
  -o-transform: rotateY(180deg);
  transform: rotateY(180deg);
  transform: rotateY(180deg);
  // color: #2d2b2b;
  // border: 1px solid #2d2b2b;
  // background: #fff;
  background: #2d2b2b;
  backface-visibility: hidden;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  p {
    margin: 1.5rem;
    line-height: 1.4;
  }
  img {
    height: 2rem;
    // border-radius: 50%;
    // border: 1px solid #fff;
  }
}
.card.flipped {
  -webkit-transform: rotateY(180deg);
  -moz-transform: rotateY(180deg);
  -o-transform: rotateY(180deg);
  transform: rotateY(180deg);
}
.card .transparentFront {
  opacity: 0;
  transition: 0.7s all;
}
.visible {
  visibility: visible;
}
</style>