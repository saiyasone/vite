<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Hello Vue" />
    <nav>
      <ul v-for="item in items" :key="item.id">
        <li>
          {{ item.title }}
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [],
      overflow: "Gig",
    };
  },

  methods: {
    loading: async function () {
      const response = await fetch(
        "https://jsonplaceholder.typicode.com/todos/1"
      );
      const data = response.json();
      this.items.push(data);
    },
  },

  created() {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
