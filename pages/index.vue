<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        Hello All About Web!
      </h1>
      <div class="links">
        <nuxt-link
          :to="{ name: 'search', query: { q: 'web' } }"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Search
        </nuxt-link>
        <a
          href="https://github.com/tarunmangukiya/all-about-web-vuejs-demo"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
        <a
          href="https://www.canva.com/design/DAEE7R1zM5E/IgVaGRX28vKKI0hge8uy1Q/view?utm_content=DAEE7R1zM5E&utm_campaign=designshare&utm_medium=link&utm_source=sharebutton"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          Presentation
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
