<template>
  <section class="order section-mt">
    <div class="container">
      <div class="order__top">
        <the-main-title title="Оформление займа" />
        <the-steps />
      </div>
      <div class="order__form">
        <the-form />
      </div>
    </div>
  </section>
</template>

<script>
import TheSteps from '../ui/steps/TheSteps.vue';
import TheMainTitle from '../layouts/TheMainTitle.vue';
import TheForm from '../ui/form/TheForm.vue';
export default {
  components: {
    TheSteps,
    TheMainTitle,
    TheForm,
  },
};
</script>

<style scoped>
.order__form {
  margin-top: 56px;
}
@media (max-width: 767px) {
  .order__form {
    margin-top: 32px;
  }
}
@media (max-width: 575px) {
  .order__form {
    margin-top: 28px;
  }
}
</style>
