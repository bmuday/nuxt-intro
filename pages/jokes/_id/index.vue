<template>
  <div>
    <nuxt-link to="/">Back to Jokes</nuxt-link>
    <h2>{{ joke }}</h2>
    <hr />
    <small>JOKE ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";

export default {
  head() {
    return {
      title: this.joke,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "The joke you prefer",
        },
      ],
    };
  },
  data() {
    return {
      joke: [],
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style></style>
