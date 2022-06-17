<template>
  <div>
    <app-header title="Choose Colors" btnText="Save & Apply" />
    <yarn-color-selector />
  </div>
</template>

<script>
import YarnColorSelector from "./components/YarnColorSelector.vue";
import AppHeader from "./components/AppHeader.vue";

export default {
  name: "App",
  components: {
    YarnColorSelector,
    AppHeader,
  },
};
</script>

<style>
/* css variables */
:root {
  --color-white: #fff;
  --color-black: #2B2C37;
  --text-size: 1.3rem;
}

html {
  font-size: 62.5%;
  box-sizing: border-box;
}

*::before,
*::after,
* {
  padding: 0;
  margin: 0;
  box-sizing: inherit;
}

body {
  line-height: 1.6;
  font-family: "Helvetica", Arial sans-serif;
  color: var(--color-black);
  /* font-size: var(--text-size); */
  font-size: 13px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

h1,
h2,
h6 {
  font-weight: font-bolder;
}

#app {
  /* font-family: Helvetica, Arial, sans-serif; */
  /* -webkit-font-smoothing: antialiased; */
  /* -moz-osx-font-smoothing: grayscale; */
  max-width: 53.7rem;
  margin: 2.4rem auto;
  padding: 2.4rem 2.4rem 1.6rem 2.4rem;
  border: 1px solid #2B2C37;
  border-radius: 1.6rem;
  /* font-family: Helvetica "sans-serif"; */
  /* font-size: 13px; */
}

.mt-8 {
  margin-top: 0.8rem;
}

.mt-24 {
  margin-top: 2.4rem;
}

/* .text-black {
  color: #2B2C37;
}
.text-sm {
  font-size: 13px;
} */
</style>
