<template>
  <div class="Container">
    <input type="number" :placeholder="placeholder" v-model="inputValue" @input="updateValue" />
  </div>
</template>

<script>
export default {
  name: 'InputComponents',
  props: {
    placeholder: String,
    value: String,
  },
  data() {
    return {
      inputValue: this.value || null,
    };
  },
  watch: {
    value(newVal) {
      this.inputValue = newVal;
    },
    inputValue(newVal) {
      this.$emit('input', newVal);
    },
  },
  methods: {
    updateValue() {
      this.$emit('input', this.inputValue);
    },
  },
};
</script>
