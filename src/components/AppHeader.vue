<template>
  <div class="app-header text-black">
    <h2>{{ title.toUpperCase() }}</h2>

    <button class="btn">
      {{ btnText }} <span class="btn-arrow">&rarr;</span>
    </button>
  </div>
</template>

<script>
export default {
  name: "app-header",
  props: {
    title: {
      String,
      default: "",
    },
    btnText: {
      title: String,
      default: "",
    },
  },
};
</script>

<style scoped>
.app-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #E3E3EC;
  padding-bottom: 1.4rem;
}
.btn {
  border-radius: 100px;
  border: 1px solid #E3E3EC;
  padding: 12px 16px;
  cursor: pointer;
  background: #fff;
}
.btn-arrow {
  margin-left: 8px;
}
</style>