<template>
  <input :value="modelValue" @input="updateInput" class="input" type="text" />
</template>

<script>
import { onUpdated } from "vue";

export default {
  name: "mp-input",
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<style>
.input {
  border: 1px solid teal;
  padding: 10px 15px;
  margin: 10px 0;
}
</style>
