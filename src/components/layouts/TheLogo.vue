<template>
  <a class="logo" href="/"
    ><span>{{ title }}</span></a
  >
</template>

<script>
export default {
  props: ['title'],
};
</script>

<style scoped>
.logo {
  font-weight: 700;
}

.logo span {
  font-size: 24px;
  line-height: 28px;
  color: var(--orange);
}
@media (max-width: 767px) {
  .logo span {
    font-size: 22px;
    line-height: 24px;
  }
}
</style>
