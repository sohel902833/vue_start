<template>
  <h1>Number {{ num }}</h1>
  <h2 v-if="num === 0">The Number Is Zero</h2>
  <h2 v-else-if="num < 0">The Number Is Negative</h2>
  <h2 v-else-if="num > 0">The Number Is Positive</h2>
  <h2 v-else>The Number Is Not Zero</h2>
  <template v-if="display">
    <h2>Md Sorab Hossain</h2>
    <h3>Sohel</h3>
  </template>
  <h2 v-show="show">Using v-show</h2>
</template>

<script>
export default {
  name: "App",
  data: () => {
    return {
      num: 0,
      display: true,
      show: false,
    };
  },
};
</script>
