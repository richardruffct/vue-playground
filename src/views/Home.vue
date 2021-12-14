<template>
  <div>
    <h1>This is the home page</h1>
    <div>
      <branded-button
        buttonText="From The Home Page"
        personName="Tom"
      ></branded-button>
    </div>
  </div>
</template>

<script>

import BrandedButton from '@/components/BrandedButton.vue';

export default {
  name: 'Home',
  components: {
    BrandedButton,
  },
};
</script>
