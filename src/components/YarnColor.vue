<template>
  <div class="yarn">
    <!-- </div> -->
    <div class="yarn-color" @click="handleClick">
      <div :style="{ backgroundColor: `${bgColor}` }" class="cone-color"></div>
      <div>
        <p class="text-grey-dark">{{ color.hex }}</p>
        <p class="text-grey-light">{{ color.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
// import colorss from '../data/yarn-colors.json';

export default {
  name: 'yarn-color',
  components: {},
  props: {
    color: {
      type: Object,
      required: true,
    },
    // colors: {
    //   type: Array,
    //   // required: true,
    // },
    isOpen: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      bgColor: this.color.hex,
      // colors: colorss,
    };
  },
  methods: {
    handleClick() {
      this.$emit('open-popup', this.color);
      // console.log(this.color)
    },
  },
};
</script>

<style scoped>
.yarn-color {
  display: flex;
  cursor: pointer;
  padding: 0.8rem;
}

.yarn-color:hover {
  background-color: #f5f5f5;
}

.cone-color {
  width: 4.8rem;
  height: 4.8rem;
  border-radius: 100%;
  margin-right: 1.6rem;
}

button {
  background: transparent;
  border: 0;
}

.yarn {
  position: relative;
  /* padding: 20px; */
}

.trigger {
  margin-bottom: 10px;
}

.content {
  /* visibility: hidden; */
  background-color: #fff;
  position: absolute;
  padding: 15px;
  width: 1264px;
  z-index: 9999;
}

.content:before {
  /* position: absolute;
  top: 50px;
  content: '';
  right: calc(50% - 10px);
  border-style: solid;
  border-width: 0 10px 10px 10px;
  border-color: transparent transparent #bfbfbf transparent; */
}

.yarn:hover .content {
  /* visibility: visible; */
  /* z-index: 9999; */
}

.content {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
}
</style>
