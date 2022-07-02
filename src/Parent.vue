<template>
  <div id="app">
    <!-- EXERCISE 01 -->
    <h1>Ex 03: Interpolation</h1>
    <Child @fetchUsers="fetchUsersService" />
  </div>
</template>

<script>
import Child from './Child.vue';

export default {
  name: 'App',
  data: () => ({
    word: 'Parent Value',
  }),
  components: {
    Child,
  },
  methods: {
    async fetchUsersService(callback) {
      const response = await this.fakeCall();
      callback(['Mario', 'David', 'John']);
    },
    fakeCall() {
      return new Promise((resolve) => {
        setTimeout(function () {
          resolve();
        }, 2000);
      });
    },
  },
};
</script>

<style></style>
