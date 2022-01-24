<template>
  <div class="home">
    home
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";

export default {
  name: "Home",
  setup() {
    console.log("setup");

    const p = ref(null);

    let name = "Mario";
    let age = 30;

    const handleClick = () => {
      p.value.classList.add("test");
      p.value.textContent = "hello wold";
    };

    return {
      name,
      age,
      handleClick,
      p,
    };
  },
};
</script>
