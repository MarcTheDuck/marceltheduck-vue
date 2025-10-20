<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/CatchCard.vue'
declare module '@tsparticles/vue3';
import Engine from '@tsparticles/engine';

const particlesLoaded = async container => {
    console.log("Particles container loaded", container);
};
const particlesOptions = {
    /* options */
};
async function particlesInit(engine: Engine): Promise<void> {
    console.log("Particles engine init", engine);
}
</script>

<template>
  <div id="app">
    <vue-particles id="tsparticles" @particles-loaded="particlesLoaded">
      <h1>test</h1>
    </vue-particles>
    <header>
      <img alt="Vue logo" class="logo" src="@/assets/MarcelTheDuck.png" width="125" height="125" />
      <vue-particles id="tsparticles" @init:="particlesInit" @particles-loaded="particlesLoaded" /> 
      <vue-particles
            id="tsparticles"
            @particles-loaded="particlesLoaded"
            URL="@/scripts/config/old_particles.json"
        />
      <div class="wrapper">
        <HelloWorld msg="Marcel Andersen" />

        <nav>
          <RouterLink to="/">About</RouterLink>
          <RouterLink to="/values">Values</RouterLink>
          <RouterLink to="/projects">Projects</RouterLink>
        </nav>
      </div>
    </header>

    <RouterView />
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
  background-color: hsla(160, 100%, 37%, 0.2);
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
