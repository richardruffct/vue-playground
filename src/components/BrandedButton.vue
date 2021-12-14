<template>
  <button
    class="branded-button"
    @click="sayHello"
  >{{ buttonText }}</button>
</template>

<script>

export default {
  name: 'BrandedButton',
  props: {
    buttonText: {
      required: true
    },
    personName: {
      required: false,
      default: 'No Person',
      type: String
    },
  },
  methods: {
    sayHello: function () {
      console.log('Hello ' + this.personName)
    },
  },
};
</script>

<style>

.branded-button {
  font-family: "Comic Sans MS";
  background-color: #3a89ac;
  font-size: 15px;
  color: #ffffff;
  border: none;
  padding: 10px;
  cursor: pointer;
}

</style>
