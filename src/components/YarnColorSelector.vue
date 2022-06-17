<template>
  <div class="yarn-color-selection">
    <div>
      <h6 class="">Create your own palette by selecting yarn colors</h6>
      <p class="mt-8">
        By mixing your own yarn colors, you can create a custom palette you
        need.
      </p>

      <h6 class="mt-24">Surprise</h6>
      <p class="mt-8">
        Sometimes the choice of colors turns out surprisingly different,
        sometimes unexpectedly beautiful. Abandon all constraints and experiment
        like an artist!
      </p>
    </div>

    <!-- <hr style="width: 500px; transform: rotate(90deg)" /> -->

    <section id="active-yarns">
      <!-- <yarn-active-color /> -->
      <div v-for="color in colors" :key="color">
        <p class="te">{{ color }}</p>
      </div>
    </section>
  </div>
</template>

<script>
// import YarnActiveColor from "./components/YarnActiveColor.vue";
import colorss from "../data/yarn-colors.json";

// import YarnActiveColor from "./components/YarnActiveColor.vue";
// import AppHeader from "./components/AppHeader.vue";
// import AppHeader from "./components/AppHeader";

export default {
  name: "YarnColorSelector",
  components: {
    // YarnActiveColor,
    // YarnColor,
    // AppHeader,
  },
  data() {
    return {
      colors: colorss,
    };
  },
  // computed: {
  //   colors() {
  //     return colorss;
  //   },
  // },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.yarn-color-selection {
  display: flex;
  margin-top: 2.4rem;
}

.text {
  margin-top: 0.8rem;
}

.te {
  font-size: 100px;
}
</style>
