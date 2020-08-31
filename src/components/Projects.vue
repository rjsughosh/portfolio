<template>
  <section class="projects-cover">
    <div class="section-divider">
      <div></div>
    </div>
    <h2>My Work</h2>
    <h3>Here are a few projects I've worked on recently. Want to see more? Email me.</h3>
    <div class="projects-wrap">
      <div
        v-on:click="openLink(project.link)"
        v-bind:class="{ clickable: project.link }"
        class="each-project flip-card"
        v-for="project in projects"
        :key="project.id"
      >
        <div class="flip-card-inner">
          <div class="project-front flip-card-front">
            <div class="project-top"></div>
            <div class="project-bottom">
              <div class="project-title">
                <div class="project-icon">
                  <img :src="getImgUrl(project.icon)" />
                </div>
                <div class="Project-tile-text">{{project.name}}</div>
              </div>
              <!-- <div class="project-tags" v-for="tag in project.tags" :key="tag">{{tag}}</div> -->
              <div class="project-tags">{{project.tag}}</div>
            </div>
          </div>
          <div class="project-back flip-card-back">
            <p>{{project.description}}</p>
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
      projects: [
        {
          id: 1,
          name: "Real-time facial emotion recognition",
          icon: "python.svg",
          tag: "Python",
          description: `Implemented a real-time application that takes continuous image input from a webcam and instantly detects the facial emotion of the person 
                        and overlays a suitable emoji on the person’s face. Trained a convolutional Neural Networks using custom data set of 50 people, CK+ and JAFFE.`,
          link: "https://github.com/rjsughosh/RealtimeFacialEmotionRecognition",
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
          tags: ["python", "sklearn"]
        },
        {
          id: 6,
          name: "Stocks Tracker",
          icon: "angular.svg",
          tag: "Angular",
          description: `A simple web app in Angular for adding stocks tracker and visualizing live data`,
          link: "https://github.com/rjsughosh/stocks-app",
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
  .each-project {
    width: 300px;
    height: 300px;
    color: #fff;
    border-radius: 5px;
    padding: 1rem;
    margin: 1rem;
  }
  .project-front {
    // padding: 1rem;
    border-radius: 5px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .project-back {
    // padding: 1rem;
    border-radius: 5px;

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    p {
      margin: 1.5rem;
      line-height: 1.4;
    }
  }
  .project-top {
    height: 150px;
  }
  .project-bottom {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .project-title {
    font-size: 1.5rem;
    display: flex;
    text-align: left;
    img {
      margin-right: 1rem;
      margin-left: 2rem;
      height: 2.5rem;
    }
  }
  .project-tags {
    //   display: inline-flex;
    text-align: center;
    margin-bottom: 1rem;
  }
}
.clickable {
  cursor: pointer;
}
.flip-card {
  // background-color: transparent;
  // width: 300px;
  // height: 300px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background: #2d2b2b;

  // color: black;
}

.flip-card-back {
  // background-color: #2980b9;
  background: #2d2b2b;

  // color: white;
  transform: rotateY(180deg);
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
</style>