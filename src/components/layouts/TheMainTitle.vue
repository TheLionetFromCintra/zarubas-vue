<template>
  <h1>{{ title }}</h1>
</template>

<script>
export default {
  props: ['title'],
};
</script>

<style scoped>
h1 {
  font-weight: 300;
  font-size: 40px;
  line-height: 40px;
  color: var(--black);
  margin-bottom: 16px;
}
@media (max-width: 767px) {
  h1 {
    font-size: 32px;
    line-height: 32px;
  }
}
@media (max-width: 575px) {
  h1 {
    font-size: 28px;
    line-height: 28px;
  }
}
</style>
