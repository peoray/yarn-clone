<template>
  <div>
    <div v-for="(color, index) in colors.slice(0, 6)" :key="color" :class="index > 0 ? 'mt-24' : null">
      <YarnColor :color="color" @open-popup="op($event)" :is-open="open" />
    </div>

  </div>
</template>

<script>
import YarnColor from './YarnColor.vue';
import {yarnColors} from '../data/yarn-colors.json';

export default {
  name: 'YarnActiveColor',
  components: {
    YarnColor,
  },
  data() {
    return {
      colors: yarnColors,
      open: false
    };
  },
  methods: {
    op(event) {
      this.$emit('open-popup', event)
    }
  },
};
</script>
