<template>
  <div v-if="show" class="user_list">
    <div v-for="(user, index) in data" class="user_item" :key="index">
      <h2>Name :{{ user?.name }}</h2>
      <h3>Roll:{{ user?.roll }}</h3>
      <h3>Email:{{ index }}</h3>
    </div>
  </div>

  <!-- object iterating   -->
  <div v-for="(value, key, index) in myInfo" :key="value">
    <h1>{{ value }} : {{ key }}, {{ index }}</h1>
  </div>

  <h1>Here Is Counter App</h1>
  <h2>{{ counter }}</h2>
  <div>
    <button @click="add()">Increment By 1</button>
    <button @click="add(5)">Increment By 5</button>
    <button @click="sub()">Decrement By 1</button>
    <button @click="sub(5)">Decrement By 5</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => {
    const data = [...new Array(40)].map((it, i) => ({
      name: "Sohel " + i,
      roll: 902833 + i,
    }));
    return {
      data: data,
      show: false,
      myInfo: {
        name: "Sohrab",
        lastName: "Hossain",
        phone: "234234",
        roll: "902833",
      },
      counter: 1,
    };
  },
  methods: {
    add(value = 1) {
      this.counter += value;
    },
    sub(value = 1) {
      this.counter -= value;
    },
  },
};
</script>

<style>
.user_list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
