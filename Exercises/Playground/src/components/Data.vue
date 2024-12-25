<template>
  <h2>Options - {{ o_firstName }} {{ o_lastName }} {{ o_heroName }}</h2>
  <h2>Composition - {{ c_firstName }} {{ c_lastName }} {{ c_HeroName }}</h2>
  <h2>Composition - {{ greet }}</h2>
  <h2>Composition - {{ greetHero }}</h2>
  <h2>Composition Reactive- {{ state.firstName }} {{ state.lastName }} {{ state.heroName }}</h2>
  <h2>Composition Reactive- {{ reactiveGreetHero }}</h2>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  setup() {
    const c_firstName = ref("Clark");
    const c_lastName = ref("Kent");
    const c_HeroName = ref("Superman");

    const greet = `Hello ${c_firstName.value}`;
    const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_HeroName.value}`;

    const state = reactive({
      firstName: "Princess",
      lastName: "Diana",
      heroName: "Wonder Woman",
    });

    const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} aka ${state.heroName}`

    return {
      c_firstName,
      c_lastName,
      c_HeroName,
      greet,
      greetHero,
      state,
      reactiveGreetHero
    };
  },
  data() {
    return {
      o_firstName: "Bruce",
      o_lastName: "Wayne",
      o_heroName: "Batman",
    };
  },
};
</script>

<style scoped></style>
