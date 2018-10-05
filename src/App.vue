<template>
  <div id="app" class="outer">
    <div class="inner">
      <div class="heading">
        <h1>Richard Wiertalla</h1>
        <h3>Developer Portfolio</h3>
        <ul class="heading__list">
          <li class="heading__list--item"><a class="heading__link" href="#">Github</a></li>
          <li class="heading__list--item"><a class="heading__link" href="#">Contact Me</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Permanent+Marker');

*, *::before, *::after {
  margin: 0;
  padding: 0;
}

body {
  font-size: 62.5%;
  font-family: sans-serif;
  font-family: 'Permanent Marker', cursive;
}

.outer {
  display: flex;
  flex-direction: column;
  
}

.inner {
  display: flex;
  justify-content: center;
}

.heading {
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  text-align: center;

  &__list {
    &--item {

    }
  }

  &__link {
    
  }
}

#app {
  height: 100vh;
  flex-direction: column;
  h1 {
    color: black;
    font-size: 3.5rem;
  }
  h3 {
    color: cornflowerblue;
    font-size: 2.5rem;
  }
}
</style>
