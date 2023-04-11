<template>
  <div>
    <h2>The about page  </h2>
    <p>This is about page the demo app for jokes</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About the app",
      meta: [
        {
          hid: "Description",
          name: "description",
          content: "The about app jokes",
        },
      ],
    };
  },
};
</script>

<style>

</style>