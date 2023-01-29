<template>
  <div>Hello {{ name }}</div>
  <h3>{{ roll }}</h3>
  <!-- using directive -->
  <div v-text="company"></div>
  <!-- javascript can use under mastas -->
  <div>{{ `${5 + 7}` }}</div>
  <!-- render html into dom -->
  <div v-html="html"></div>
  <h2 :id="htmlId">Heading</h2>
  <button :disabled="isButtonDisabled">Click Me!</button>

  <!-- importing class -->
  <h1 class="underline">Underline text</h1>
  <h1 class="underline" :class="status">Status {{ status }}</h1>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h4 :class="isSoldout ? 'sold-out' : 'new'">Soldout?Movie</h4>
  <!-- array bind class  -->
  <h3 :class="[isSoldout ? 'sold-out' : 'new', isPromoted && 'promoted']">
    Array Classes
  </h3>
  <!-- object conditional text  -->
  <h2
    :class="{
      promoted: isPromoted,
      'sold-out': isSoldout,
    }"
  >
    Object Conditional Movie
  </h2>
  <!-- inline css  -->
  <h3
    :style="{
      color: highlightColor,
      'font-size': `${headerSize}px`,
      padding: '20px',
      'background-color': 'red',
    }"
  >
    Inline Style Css From State
  </h3>
  <h2 :style="headerStyleObj">Style Object</h2>

  <!-- inline css with array object -->
  <h1 :style="[baseStyleObject, successStyleObject]">Inline Style Array</h1>
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
      highlightColor: "green",
      headerSize: 60,
      headerStyleObj: {
        color: "orange",
        fontSize: "50px",
        padding: "20px",
        background: "red",
      },
      baseStyleObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
      },
      successStyleObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
      },
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
