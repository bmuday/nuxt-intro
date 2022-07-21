<template>
  <div>
    <h1>About DadJokes</h1>
    <p>This is an app that display corny dad jokes</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About the App",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes",
        },
      ],
    };
  },
};
</script>
