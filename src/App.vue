<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
    <button @click="sebd">sebd</button>
  </div>
  <hellow :data="data" :show="show" />
</template>
<script>
import { ref } from "vue";
import hellow from "./components/HelloWorld";
export default {
  components: {
    hellow
  },
  setup() {
    const show = ref(false);
    const sebd = () => {
      show.value = !show.value;
      data.value.name = "fuck vue3";
    };
    const data = ref({
      name: "cookjiedddd",
      age: 0,
      hasDick: false,
      someData: {
        subName: "",
        subArr: [5, 6, 9, 82, 4],
        subBoo: false,
        subNumber: 0
      },
      arr: [9, 8, 7, 6, 5, 4, 3, 2, 1]
    });
    return {
      show,
      data,
      sebd
    };
  }
};
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
