<template>

  <div id="app">
    <div id="app-container" class="acid-text">
      <img alt="Vue logo" src="./assets/logo.png">
      <HeroHero />
      <AppTitle />
      <APIrequest />
    </div>
  </div>
</template>

<script>
import AppTitle from './components/AppTitle.vue'
import HeroHero from './components/HeroHero.vue'
import APIrequest from './components/APIrequest.vue'


export default {
  name: 'App',
  components: {
    AppTitle,
    HeroHero,
    APIrequest
  }
}
</script>

<style lang="scss">

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  // margin-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: black;
  height: 100vh;
}

template{
  background-color: black;
}

#app-container{
  height: 50vh;
  width: 50vw;
}

.acid-text{
    /* font-size: 2rem; */
    display: inline-block;
    cursor: pointer;
    text-decoration: none;
    background-color: #202531;
    color: yellowgreen;
    border: 0.125em solid yellowgreen;
    padding: 0.25em 1em;
    border-radius: 0.25em;

    text-shadow: 0 0 0.125em white,
    0 0 0.125 currentColor;

    box-shadow: inset 0 0 0.5em 0 yellowgreen,
    0 0 0.5em 0 yellowgreen;

    position: relative;

    transition: background-color 0.5s;
}


.acid-text::before{
    pointer-events: none;
    content: "";
    position: absolute;
    background-color: yellowgreen;
    top: 120%;
    left: 0;
    width: 100%;
    height: 100%;

    transform: perspective(1em) rotateX(40deg) scale(1, 0.35);
    filter: blur(2em);
    opacity: 0.7;
}

.acid-text::after{
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    box-shadow: 0 0 2em yellowgreen;
    opacity: 1;
    background-color: yellowgreen;
    z-index: -1;
    transition: 1s linear;
}

.acid-text:hover,
.acid-text:focus{
    background-color: yellowgreen;
    color: #202531;
    text-shadow: none;
}

.acid-text:hover::after{
    opacity: 1;
}
</style>
