<template>
  <button type="{{type}}">
    <span>{{ title }}</span>
  </button>
</template>

<script>
export default {
  props: ['title', 'type'],
};
</script>

<style scoped>
button {
  border: none;
  background: linear-gradient(
      180deg,
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 0.2) 100%
    ),
    var(--orange-light);
  background-blend-mode: overlay, normal;
  border-radius: 8px;
  cursor: pointer;
  text-align: center;
  padding: 12px;
  width: 100%;
  max-width: 321px;

  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: var(--white);
}
</style>
