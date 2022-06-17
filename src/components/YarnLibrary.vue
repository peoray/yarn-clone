<template>
  <div class="vue-modal" v-show="open" @click="$emit('close')" >
    <transition name="slide">
      <div class="vue-modal-inner">
        <div class="vue-modal-content">
          <slot />
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'yarn-library',
  props: {
    open: {
      type: Boolean,
      default: true,
    },
  },
};
</script>

<style scoped>
.vue-modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  overflow-x: hidden;
  overflow-y: auto;
  background-color: rgba(0, 0, 0, 0.4);
  z-index: 1;

  display: flex;
	align-items: center;
	justify-content: center;
}

.vue-modal-inner {
  max-width: 500px;
  margin: 2rem auto;
  display: flex;
  align-items: center;
}

.vue-modal-content {
  position: relative;
  background-color: #fff;
  /* border: 1px solid rgba(0, 0, 0, 0.3); */
  /* background-clip: padding-box; */
  /* border-radius: 0.3rem; */
  padding: 1rem;

  display: grid;
  grid-template-columns: repeat(15, 1fr);
  gap: 5px;
  /* height: 1000px; */
}
</style>
