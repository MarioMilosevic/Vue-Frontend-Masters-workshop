<script>
import BenderStatistics from "./components/BenderStatistics.vue";
import UserCard from "./components/UserCard.vue";
export default {
  components: {
    BenderStatistics,
    UserCard,
  },
  data() {
    return {
      message: "Hello it works",
      listOfNumbers: [
        {
          name: 1,
          id: 1,
          list: [1, 2, 3],
        },
        {
          name: 2,
          id: 2,
          list: [1, 2, 3],
        },
        {
          name: 3,
          id: 3,
          list: [1, 2, 3],
        },
        {
          name: 4,
          id: 4,
          list: [1, 2, 3],
        },
        {
          name: 5,
          id: 5,
          list: [1, 2, 3],
        },
      ],
      characterList: [
        {
          name: "Aang",
          element: ["Air", "Earth", "Water", "Fire"],
        },
        {
          name: "Zuko",
          element: ["Fire"],
        },
        {
          name: "Toph",
          element: ["Earth"],
        },
        {
          name: "Katakara",
          element: ["Water"],
        },
      ],
      userData: {
        name: "Mario",
        preferredFramework: "vue",
        favoriteFood: "pizza",
        favoriteNumbers: [8, 2, 19],
      },
    };
  },
};
</script>

<template>
  <UserCard :user="userData"/>
  <!-- <BenderStatistics :characters="characterList" /> -->

  <!-- <h2>Characters</h2>
  <p v-if="characterList.length === 0">There are no characters</p>
  <ul v-else-if="characterList.length % 2 === 0">
    <li
      v-for="(character, index) in characterList"
      :key="`even-character-${index}`"
    >
      <p>{{ character.name }}</p>
      <button @click="favoriteCharacter(character)">Favorite</button>
    </li>
  </ul>
  <p v-else>There are odd characters</p>
  <hr />
  <p v-if="message.length % 2 === 0">Even:{{ message.toUpperCase() }}</p>
  <p v-else>Odd:{{ message }}</p>
  <ul v-for="(item, index) in listOfNumbers" :key="`item-${index}`">
    <li>
      {{ item.id }}
      <ul>
        <li v-for="(number, index) in item.list" :key="`number-${index}`">
          {{ number }}
        </li>
      </ul>
    </li>
  </ul> -->
</template>
