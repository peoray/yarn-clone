<template>
  <div>
    <div class="cone-color"></div>
    <div>
      <p>{{ color.hex }}</p>
      <p>{{ color.name }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "yarn-color",
  props: {
    color: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      bgColor: this.props.color.hex,
    };
  },
};
</script>

<style scoped>
.cone-color {
  background-color: v-bind(bgColor);
}
</style>