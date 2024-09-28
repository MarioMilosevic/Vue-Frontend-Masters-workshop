<script>
export default {
    props: {
        name: {
            typeof: String,
            default:"John Doe"
        },
        favoriteFood: {
            typeof: String,
            default:"Steak"
        },
        // user: {
        //     typeof: Object,
        //     required : true
        // },
        // favoriteFood: {
        //     typeof: String,
        //     required: true
        // },
    }
};
</script>

<template>
  <h1>User: {{ name }}</h1>
  <p>Favorite Food: {{ favoriteFood }}</p>
</template>
