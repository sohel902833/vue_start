<template>
  <div>Hello {{ name }}</div>
  <h3>{{ roll }}</h3>
  <!-- using directive -->
  <div v-text="company"></div>
  <!-- javascript can use under mastas -->
  <div>{{ `${5 + 7}` }}</div>
  <!-- render html into dom -->
  <div v-html="html"></div>
  <h2 v-bind:id="htmlId">Heading</h2>
  <button v-bind:disabled="isButtonDisabled">Click Me!</button>

  <!-- importing class -->
  <h1 class="underline">Underline text</h1>
  <h1 class="underline" v-bind:class="status">Status {{ status }}</h1>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h4 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout?Movie</h4>
  <!-- array bind class  -->
  <h3 v-bind:class="[isSoldout ? 'sold-out' : 'new', isPromoted && 'promoted']">
    Array Classes
  </h3>
  <!-- object conditional text  -->
  <h2
    v-bind:class="{
      promoted: isPromoted,
      'sold-out': isSoldout,
    }"
  >
    Object Conditional Movie
  </h2>
</template>

<script>
export default {
  name: "App",
  data: () => {
    return {
      name: "Md Sohrab Hossain Sohel",
      roll: "902833",
      company: "Zaagsys",
      html: "<h3 onclick='alert('You Hacked')'>Bolder Text</h3>",
      htmlId: "hello-sohel",
      isButtonDisabled: true,
      status: "danger",
      isPromoted: true,
      isSoldout: false,
    };
  },
};
</script>

<style>
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: green;
}
.sold-out {
  color: red;
}
</style>
