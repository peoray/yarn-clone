<template>
  <div class="yarn-color-selection">
    <div class="item-1">
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

    <section id="active-yarns item-1">
      <yarn-active-color @open-popup="openModal($event)" />

      <YarnLibrary :open="isOpen" @close="isOpen = false" class="grid">
        <button
          v-for="(color, index) in colors"
          :key="index"
          :style="{ backgroundColor: `${color.hex}` }"
          :class="color.pantoneId === selectedColorId ? 'selected' : null"
          class="cone-color" @click="getColor(color)"
        ></button>
      </YarnLibrary>
    </section>
  </div>
</template>

<script>
import YarnActiveColor from './YarnActiveColor';
import { yarnColors } from '../data/yarn-colors.json';
import YarnLibrary from './YarnLibrary.vue';

export default {
  name: 'YarnColorSelector',
  components: {
    YarnActiveColor,
    YarnLibrary,
  },
  data() {
    return {
      colors: yarnColors,
      isOpen: false,
      selectedColorId: null,
      colorChange: null
    };
  },
  methods: {
    openModal(event) {
      this.isOpen = true;
      this.selectedColorId = event.pantoneId;
    },
    getColor(color) {
      this.colorChange = color
      console.log(event)

    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.item-a {
  grid-area: content;
}
.item-b {
  grid-area: cones;
}
.yarn-color-selection {
  /* display: flex; */
  /* justify-content: space-between; */
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  /* justify-content: space-around; */
  grid-template-areas:
    'content . cones'
    'content . cones'
    'content . cones';
  margin-top: 2.4rem;
}

.text {
  margin-top: 0.8rem;
}

.te {
  font-size: 100px;
}
.grid {
  display: flex;
}

.cone-color {
  display: flex;
  width: 3.2rem;
  height: 3.2rem;
  border-radius: 100%;
  cursor: pointer;
  /* margin-right: 1.6rem; */
}

.selected {
  border: 2px solid blue;
    /* width: 4.8rem; */
  /* height: 4.8rem; */
}

button {
  background: transparent;
  border: 0;
}
</style>
