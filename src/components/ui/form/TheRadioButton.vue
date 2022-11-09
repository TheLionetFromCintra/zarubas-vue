<template>
  <label class="form__radio-wrapper">
    <input
      type="radio"
      name="gender"
      class="form__radio"
      checked
      :value="option"
      @change="$emit('update:modelValue', $event.target.value)"
    />
    <span>{{ option }}</span>
  </label>
</template>

<script>
export default {
  props: ['option'],
  emits: ['update:modelValue'],
};
</script>

<style scoped>
.form__radio-wrapper span {
  display: block;
  font-weight: 500;
  position: relative;
  font-size: 12px;
  line-height: 16px;
  padding: 16px 13px;
  border-radius: 8px;
  transition: background-color 0.3s linear, color 0.3s linear;
}

.form__radio-wrapper input:checked ~ span {
  background-color: var(--blue);
  color: var(--white);
}

.form__radio {
  position: absolute;
  opacity: 0;
  z-index: -1;
}
</style>
