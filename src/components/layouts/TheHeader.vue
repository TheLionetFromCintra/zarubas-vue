<template>
  <header class="header">
    <div class="container">
      <div class="header__wrapper">
        <the-logo title="Zarubas" />
      </div>
    </div>
  </header>
</template>

<script>
import TheLogo from './TheLogo.vue';
export default {
  components: {
    TheLogo,
  },
};
</script>

<style scoped>
.header {
  padding-top: 33px;
}
@media (max-width: 767px) {
  .header {
    padding-top: 20px;
  }
}
</style>
