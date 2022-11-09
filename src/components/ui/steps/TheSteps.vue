<template>
  <ul class="steps d-flex align-items-center">
    <li
      class="step"
      :class="i === 0 ? 'active' : ''"
      v-for="(step, i) in steps"
      :key="step"
    >
      {{ step.name }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      steps: [
        { name: 'Анкета' },
        { name: 'СМС' },
        { name: 'Карта' },
        { name: 'Получить займ' },
      ],
    };
  },
};
</script>

<style scoped>
.step {
  font-weight: 300;
  font-size: 16px;
  line-height: 24px;
  color: var(--black);
  opacity: 0.5;
  position: relative;
  padding-bottom: 6px;
}

.step.active::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: var(--blue-light);
  border-radius: 8px;
}

.step.active {
  opacity: 1;
  font-weight: 400;
}

.step + .step {
  margin-left: 24px;
}

@media (max-width: 767px) {
  .step {
    font-size: 14px;
    line-height: 20px;
  }

  .step + .step {
    margin-left: 20px;
  }
}
@media (max-width: 575px) {
  .step + .step {
    margin-left: 16px;
  }
}
</style>
