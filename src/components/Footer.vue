<template>
  <footer>
    <div class="footer-left">© {{year()}} by Sughosh Jahagirdar. All rights reserved.</div>
    <div class="footer-right">
      Designed with
      <span>❤</span> by
      <a href="https://abhisheknairofficial.com/">6foot4</a>
    </div>
  </footer>
</template>

<script>
export default {
  methods: {
    year() {
      var d = new Date();
      var n = d.getFullYear();
      return n;
    }
  }
};
</script>

<style lang="scss">
footer {
  background: #4b4b4b;
  height: 60px;
  display: flex;
  justify-content: space-between;
  padding: 1rem 10rem;
  color: #fff;
  font-size: 1rem;
  align-items: center;
}

.footer-right {
  span {
    color: red;
    margin: 0 3px;
    padding: 0 3px;
  }
  a {
    text-decoration: none;
    color: #fff;
  }
}
@media only screen and (max-width: 600px) {
  footer {
    padding: 0.5rem;
    font-size: 1rem;
  }
}
</style>