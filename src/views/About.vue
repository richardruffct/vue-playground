<template>
  <div class="about">
    <h1>This is an about page</h1>
    <branded-button
      buttonText="From The About Page"
    ></branded-button>
  </div>
</template>

<script>

import BrandedButton from '@/components/BrandedButton.vue';

export default {
  components: {
    BrandedButton,
  },
};

</script>
