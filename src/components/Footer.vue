<template>
  <footer>
    <div class="footer-left">Sughosh Raviraj Jahagirdar © 2020</div>
    <div class="footer-right">
      Designed with
      <span>❤</span> by 6foot4
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss">
footer {
  background: #4b4b4b;
  height: 60px;
  display: flex;
  justify-content: space-between;
  padding: 1rem 10rem;
  color: #fff;
  font-size: 1.2rem;
  align-items: center;
}

.footer-right {
  span {
    color: red;
    margin: 0 3px;
    padding: 0 3px;
  }
}
@media only screen and (max-width: 600px) {
  footer {
    padding: 0.5rem;
    font-size: 1rem;
  }
}
</style>