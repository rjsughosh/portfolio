<template>
  <section class="skills-cover">
    <h2>My Skills</h2>
    <h3>Current stats. I hope to keep improving this list</h3>
    <div class="skills-badge-wrap">
      <div
        class="skills-badge skills-badge-glow"
        :class="item.class"
        v-for="item in badges"
        :key="item.name"
      >
        <img :title="item.name" :src="getImgUrl(item.icon)" v-bind:alt="item.icon" />
        <div>{{item.name}}</div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      badges: [
        {
          name: "HTML 5",
          icon: "html5.svg",
          class: "gold"
        },
        {
          name: "CSS 3",
          class: "gold",
          icon: "css3.svg"
        },
        {
          name: "JavaScript",
          class: "gold",
          icon: "javascript.svg"
        },
        {
          name: "Angular",
          class: "gold",
          icon: "angular.svg"
        },
        {
          name: "VueJS",
          class: "gold",
          icon: "vue.svg"
        },
        {
          name: "React",
          class: "silver",
          icon: "react.svg"
        },
        {
          name: "Bootstrap",
          class: "silver",
          icon: "bootstrap.svg"
        },
        {
          name: "Python",
          class: "silver",
          icon: "python.svg"
        },
        {
          name: "Java",
          class: "silver",
          icon: "java.svg"
        },
        {
          name: "MongoDB",
          class: "silver",
          icon: "mongodb.svg"
        },
        {
          name: "Machine Learning",
          class: "silver",
          icon: "connection.svg"
        },
        {
          name: "AWS",
          class: "bronze",
          icon: "amazonaws.svg"
        },
        {
          name: "C++",
          class: "bronze",
          icon: "cplusplus.svg"
        },
        {
          name: "SQL",
          class: "bronze",
          icon: "mysql.svg"
        }
      ]
    };
  },
  methods: {
    getImgUrl(img) {
      return require("../assets/icons/icons-white/" + img);
    }
  }
};
</script>

<style scoped lang="scss">
.skills-cover {
  min-height: 100vh;
  background: #fffbfc;
  color: #000;

  .skills-badge-wrap {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    // display: flex;
    padding: 3rem 15rem 3rem 15rem;
    // justify-content: space-evenly;
    // flex-wrap: wrap;
    .skills-badge {
      position: relative;

      border-radius: 5px;
      display: inline-flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      height: 200px;
      width: 180px;
      margin: 0.5rem;
      img {
        height: 100px;
        margin: 1rem 0;
      }
    }
  }
}
.gold {
  background: #ffd700;
  // type2
  background: linear-gradient(to left, #ffd700 0%, #d4af37 100%);
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    color-stop(0%, #d4af37),
    color-stop(100%, #d4af37)
  );
  background: -webkit-linear-gradient(to right, #d4af37 0%, #d4af37 100%);
  background: -moz-linear-gradient(to right, #d4af37 0%, #d4af37 100%);
  background: -o-linear-gradient(to right, #d4af37 0%, #d4af37 100%);
  background: -ms-linear-gradient(to right, #d4af37 0%, #d4af37 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#d4af37', endColorstr='#d4af37', GradientType=0);
  box-shadow: inset 0 1px 0 #d4af37;
  -webkit-box-shadow: inset 0 1px 0 #d4af37;
  -moz-box-shadow: inset 0 1px 0 #d4af37;
}

.silver {
  background: #bfbfbf;
  background: linear-gradient(to left, #bfbfbf 0%, #999 100%);
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    color-stop(0%, #bfbfbf),
    color-stop(100%, #999)
  );
  background: -webkit-linear-gradient(to right, #bfbfbf 0%, #999 100%);
  background: -moz-linear-gradient(to right, #bfbfbf 0%, #999 100%);
  background: -o-linear-gradient(to right, #bfbfbf 0%, #999 100%);
  background: -ms-linear-gradient(to right, #bfbfbf 0%, #999 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#bfbfbf', endColorstr='#999', GradientType=0);
  box-shadow: inset 0 1px 0 #999;
  -webkit-box-shadow: inset 0 1px 0 #999;
  -moz-box-shadow: inset 0 1px 0 #999;
}
.bronze {
  background: #c27c34;
  background: linear-gradient(to left, #c27c34 0%, #7f4600 100%);
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    color-stop(0%, #c27c34),
    color-stop(100%, #7f4600)
  );
  background: -webkit-linear-gradient(to right, #c27c34 0%, #7f4600 100%);
  background: -moz-linear-gradient(to right, #c27c34 0%, #7f4600 100%);
  background: -o-linear-gradient(to right, #c27c34 0%, #7f4600 100%);
  background: -ms-linear-gradient(to right, #c27c34 0%, #7f4600 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#c27c34', endColorstr='#7F4600', GradientType=0);
  box-shadow: inset 0 1px 0 #7f4600;
  -webkit-box-shadow: inset 0 1px 0 #7f4600;
  -moz-box-shadow: inset 0 1px 0 #7f4600;
}
.border-bottom {
  div {
    border: 1px solid #999;
  }
  margin: 0 40%;
}

// shiny starts here
@mixin center($extend: true) {
  @if $extend {
    @extend %center;
  } @else {
    position: absolute;
  }
}

%center {
  @include center($extend: false);
}

.skills-badge-glow {
  @include center;
  transition: 0.6s;
  overflow: hidden;

  &:before {
    content: "";
    display: block;
    position: absolute;
    background: rgba(255, 255, 255, 0.5);
    width: 60px;
    height: 100%;
    left: 0;
    top: 0;
    opacity: 0.5;
    filter: blur(30px);
    transform: translateX(-100px) skewX(-15deg);
  }
  &:after {
    content: "";
    display: block;
    position: absolute;
    background: rgba(255, 255, 255, 0.2);
    width: 30px;
    height: 100%;
    left: 30px;
    top: 0;
    opacity: 0;
    filter: blur(5px);
    transform: translateX(-100px) skewX(-15deg);
  }
  &:hover {
    // background: #338033;
    // cursor: pointer;
    &:before {
      transform: translateX(300px) skewX(-15deg);
      opacity: 0.6;
      transition: 0.7s;
    }
    &:after {
      transform: translateX(300px) skewX(-15deg);
      opacity: 1;
      transition: 0.7s;
    }
  }
}
// shiny ends here

@media only screen and (max-width: 1025px) {
  .skills-cover {
    .skills-badge-wrap {
      padding: 3rem 6rem;
    }
  }
}

@media only screen and (max-width: 600px) {
  .skills-cover {
    min-height: 100vh;
    background: #fffbfc;
    color: #000;

    .skills-badge-wrap {
      // display: flex;
      padding: 3rem 0rem 3rem 0rem;
      // justify-content: space-evenly;
      // flex-wrap: wrap;
    }
  }
}
</style>
