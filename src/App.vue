<template>
  <div id="app">
    <div class="outer">
      <div class="inner">
        <div class="heading">
          <h1>Richard Wiertalla</h1>
          <h3>Developer Portfolio</h3>
          <ul class="heading__list">
            <li class="heading__list--item">
              <a class="heading__link" href="https://github.com/wiertar">
                <i class="icon fab fa-github"></i>
                Github
              </a>
            </li>
            <li class="heading__list--item">
              <a class="heading__link" href="#">
                <i class="icon far fa-envelope"></i>
                  Contact
              </a>
            </li>
          </ul>
        </div>
      </div>
      <section class="content">
        <div class="content--projects">
          <h2>Projects</h2>
          <ul class="projects__list">
            <li class="projects__list--item">Project 1</li>
            <li class="projects__list--item">Project 2</li>
            <li class="projects__list--item">Project 3</li>
            <li class="projects__list--item">Project 4</li>
          </ul>
        </div>
        <div class="content--skills">
          <h2>Skills</h2>
          <ul class="skills__list">
            <li class="skills__list--item">{{ skills }}<span>&#10003;</span></li>
            <li class="skills__list--item">test</li>
            <li class="skills__list--item">test</li>
            <li class="skills__list--item">test</li>
            <li class="skills__list--item">test</li>
            <li class="skills__list--item">test</li>
          </ul>
        </div>
      </section>
    </div>
    <footer class="footer">
      <div class="footer__content">
        <span>
          Made with Vue, Node.js, Travis CI, Heroku, Github, and with lots of
          <i class="fas fa-heart"></i>
        </span>
      </div>
    </footer>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'app',
  data() {
    return {
      projects: null,
      skills: null,
    };
  },
  mounted() {
    axios
      .get('https://gentle-waters-43988.herokuapp.com/')
      .then((res) => {
        this.skills = res.data;
      });
  },
  components: {
  },
};
</script>

<style lang="scss">
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-size: 62.5%;
  font-family: sans-serif;
  font-family: 'Permanent Marker', cursive;
}

h1 {
  color: black;
  font-size: 3.5rem;
}

h2 {color: teal;
  color: teal;
  font-size: 2.5rem;
}

h3 {
  color: cornflowerblue;
  font-size: 2rem;
}

.icon {
  font-size: 1.5rem;
  margin-right: 8px;
}

.fa-heart {
  color: red;
}

.u_serif {
  font-family: 'Rubik', sans-serif;
}

.outer {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
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
  width: inherit;
  &__list {
    display: flex;
    justify-content: space-around;
    list-style: none;
    border-top: 5px dashed black;
    margin-top: 1rem;
    padding-top: 2rem;
  }
  &__link {
    font-size: 1.5rem;
    text-decoration: none;
    font-family: sans-serif;
    border: 3px solid cornflowerblue;
    border-radius: 5px;
    padding: .25rem 1rem;
    min-width: 10rem;
    display: inline-block;
    color: white;
    background-color: cornflowerblue;
  }
}

.content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-top: 3rem;
  &--projects {
   text-align: center;
  }
  &--skills {
    margin-top: 3rem;
    text-align: center;
  }
}

.skills {
  &__list {
    display: flex;
    margin-top: 1rem;
    flex-direction: column;
    list-style-type: none;
    font-family: 'Rubik', sans-serif;
    &--item {
      font-size: 1rem;
    }
  }
}

.projects {
  &__list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 1rem;
    list-style-type: none;
    font-family: 'Rubik', sans-serif;
    &--item {
      font-size: 1rem;
      padding: 5rem;
      margin: .5rem;
      border: 3px solid black;
    }
  }
}

.footer {
  &__content {
    margin-top: 3rem;
    display: flex;
    justify-content: center;
    background-color: #4c56a3;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Cg fill-rule='evenodd'%3E%3Cg fill='%23000000' fill-opacity='0.4'%3E%3Cpath opacity='.5' d='M96 95h4v1h-4v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9zm-1 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9z'/%3E%3Cpath d='M6 5V0H5v5H0v1h5v94h1V6h94V5H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    height: 100px;
    font-size: 1rem;
    font-family: 'Rubik', sans-serif;
    color: white;
    span {
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
  }
}

@media (max-width: 364px) {
  .heading {
    &__list {
      flex-direction: column;
    }
    &__link {
    }
  }
}

#app {
  height: 100vh;
  flex-direction: column;
}
</style>
