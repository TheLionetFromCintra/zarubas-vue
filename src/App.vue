<template>
  <the-header />
  <the-order-section />
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheOrderSection from './components/layouts/TheOrderSection.vue';
export default {
  name: 'App',
  components: {
    TheHeader,
    TheOrderSection,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');
@import url('./assets/styles/reset.css');

:root {
  --black: #0b161f;
  --white: #ffffff;
  --orange: #ff5c00;
  --orange-light: #ff8800;
  --blue: #0063ff;
  --blue-light: #2f80ed;
  --gray: #808080;
}

html {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  -webkit-box-sizing: inherit;
  box-sizing: inherit;
}

img,
svg {
  max-width: none;
  height: 100%;
}

body {
  font-family: 'Roboto', sans-serif;
  overflow-x: hidden;
  position: relative;
  background-color: var(--white);
  color: var(--black);
  font-weight: 400;
  font-style: normal;
}
.d-flex {
  display: flex;
}
.align-items-center {
  align-items: center;
}
.flex-column {
  flex-direction: column;
}
.justify-content-between {
  justify-content: space-between;
}
.container {
  width: 100%;
  max-width: 744px;
  padding: 0 40px;
  margin: 0 auto;
}
.section-mt {
  margin: 64px 0;
}
.form__label {
  font-size: 14px;
  line-height: 20px;
  display: inline-block;
  margin-bottom: 4px;
  font-weight: 300;
  cursor: default;
}
@media (max-width: 767px) {
  .container {
    max-width: 100%;
    padding: 0 24px;
  }
  .section-mt {
    margin: 48px 0;
  }
}
@media (max-width: 575px) {
  .container {
    padding: 0 15px;
  }

  .section-mt {
    margin: 36px 0;
  }
  .form__label {
    font-size: 13px;
  }
}
</style>
