<template>
  <label class="form__item d-flex flex-column">
    <span class="form__label">{{ label }}</span>
    <input
      type="text"
      @input="$emit('update:modelValue', $event.target.value)"
      :value="modelValue"
      :maxlength="length"
    />
  </label>
</template>

<script>
export default {
  props: ['modelValue', 'length', 'label'],
  emits: ['update:modelValue'],
};
</script>

<style scoped>
input {
  border: 1px solid;
  border-color: rgba(128, 128, 128, 0.4);
  border-radius: 8px;
  max-height: 48px;
  background-color: inherit;
  padding: 12px 14px 12px 16px;
  font-weight: 500;
  font-family: inherit;
  font-size: 16px;
  line-height: 24px;
}
@media (max-width: 767px) {
  input {
    font-size: 14px;
    line-height: 20px;
  }
}
</style>
