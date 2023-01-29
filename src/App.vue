<template>
  <div>Hello {{ name }}</div>
  <h3>{{ roll }}</h3>
  <!-- using directive -->
  <div v-text="company"></div>
  <!-- javascript can use under mastas -->
  <div>{{ `${5 + 7}` }}</div>
  <!-- render html into dom -->
  <div v-html="html"></div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "Md Sohrab Hossain Sohel",
      roll: "902833",
      company: "Zaagsys",
      html: "<h3 onclick='alert('You Hacked')'>Bolder Text</h3>",
    };
  },
};
</script>
