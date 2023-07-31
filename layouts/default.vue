<template>
  <div>
    <header>
      <top-bar />
    </header>

    <main>
      <Nuxt />
    </main>

    <footer></footer>
  </div>
</template>

<script>
  export default {
  }
</script>

<style lang="scss">
  :root {
    // vars
    --theme_primary: #3656F5;
    --theme_white: #fff;
    --theme_black: #050c26;
    --theme_red: #ff6161;
    --theme_orange: #FFA953;
    --theme_green: #48CF79;

    font-family: 'Lato';
    background: #F6F9FD;
  }

  * {
    font-family: 'Lato';
  }

  body {
    margin: 0;
  }

  h1, h2, h3, h4, h5, h6 {
    margin: 0;
    color: var(--theme_black);
    font-weight: bold;
  }

  a, p, span {
    margin: 0;
    color: #7B8090;
  }

  a {
    text-decoration: none;
    cursor: pointer;
  }

  #__layout {
    margin-top: calc(var(--margin-top) + 0px);
  }
</style>
