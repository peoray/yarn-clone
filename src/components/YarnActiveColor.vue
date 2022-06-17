<template>
  <div>
    <YarnColor />

    <p color in colors>{{ color.name }}</p>
  </div>
</template>

<script>
import YarnColor from "./components/YarnColor.vue";
import colors from "../data/yarn-colors.json";

export default {
  name: "YarnActiveColor",
  components: {
    YarnColor,
  },
};
</script>