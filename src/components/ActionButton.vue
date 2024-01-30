<template>
  <div class="Container">
    <button class="btn" @click="handleClick">{{ title }}</button>
  </div>
</template>

<script>
export default {
  name: 'ActionButton',
  props: {
    title: String,
    click: Function,
  },
  methods: {
    handleClick() {
      if (this.click && typeof this.click === 'function') {
        this.click();
      }
    },
  },
}
</script>

<style scoped>
.Container {
  display: flex;
  width: 100%;
  justify-content: space-evenly;
  align-items: center;
  margin-top: 10px;
}

.btn {
  width: 30px;
  height: 20px;
  color: #000;
}
</style>
