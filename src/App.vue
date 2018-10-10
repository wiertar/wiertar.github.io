<template>
  <div id="app">
    <div class="col">
      <div class="row">
        <div class="heading">
          <div class="heading__text">
            <h1>Richard Wiertalla</h1>
            <h3>Developer Portfolio</h3>
          </div>
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
      <div class="row">
        <section class="content">
          <div class="content--projects">
            <h2>Projects</h2>
            <ul class="projects__list">
              <li class="projects__list--item" v-for="(project, index) in projects" :key="index" :class="{background: url(project.ImgBase64)}">
                {{ project.Name }}
                </li>
            </ul>
          </div>
        </section>
      </div>
      <div class="row">
        <section class="content">
          <div class="content--skills">
            <h2>Skills</h2>
            <ul class="skills__list">
              <li class="skills__list--item" v-for="(skill, index) in skills" :key="index">
                {{ skill }}
                <span>&#10003;</span>
              </li>
            </ul>
          </div>
        </section>
      </div>
      <footer class="footer row">
      <div class="footer__content">
        <span>
          Made with Vue, Node.js, Travis CI, Heroku, Github, and with lots of
          <i class="fas fa-heart"></i>
        </span>
      </div>
    </footer>
    </div>
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
        this.skills = res.data.skillsRes[0].Skills;
        this.projects = res.data.projectsRes[0].Projects;
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

h2 {
  color: forestgreen;
  font-size: 2.5rem;
}

h3 {
  color: dodgerblue;
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

.col {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  min-height: 1200px;
  overflow-y: auto;
}

.row {
  display: flex;
  justify-content: center;
  align-items: flex-start;
}

.heading {
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  text-align: center;
  width: inherit;
  &__text {
    border-bottom: 5px dashed black;
    padding-bottom: 1rem;
  }
  &__list {
    display: flex;
    justify-content: space-around;
    list-style: none;
    padding-top: 1rem;
  }
  &__link {
    font-size: 1.5rem;
    text-decoration: none;
    font-family: sans-serif;
    border: 3px solid dodgerblue;
    padding: .25rem 1rem;
    min-width: 10rem;
    display: inline-block;
    color: white;
    background-color: dodgerblue;
  }
}

.content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  &--projects {
   text-align: center;
  }
  &--skills {
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
  display: block;
  &__content {
    margin-top: 1rem;
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

@media (max-width: 400px) {
  body {
    font-size: 1.5%;
  }
  .heading {
    &__list {
      flex-direction: column;
      margin-top: 1rem;
      padding: 0;
    }
    &__link {
      margin: 1rem 0;
      min-width: 75%;
    }
  }
}

#app {
  height: 100vh;
}
</style>
