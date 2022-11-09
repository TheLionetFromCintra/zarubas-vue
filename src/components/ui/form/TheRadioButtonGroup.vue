<template>
  <label class="form__item d-flex flex-column">
    <span class="form__label">{{ label }}</span>
    <div
      class="form__radio-helper d-flex align-items-center justify-content-between"
    >
      <the-radio-button
        v-for="option in options"
        :option="option"
        :key="option"
      />
    </div>
  </label>
</template>

<script>
import TheRadioButton from './TheRadioButton.vue';
export default {
  components: {
    TheRadioButton,
  },
  props: ['options', 'label'],
};
</script>

<style scoped>
.form__radio-helper {
  border: 1px solid;
  border-color: rgba(128, 128, 128, 0.4);
  border-radius: 8px;
  max-height: 48px;
  background-color: inherit;
}

@media (max-width: 575px) {
  .form__radio-helper {
    max-width: 158px;
  }
}
</style>
