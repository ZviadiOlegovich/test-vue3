<template>
  <form @submit.prevent>
    <h4>Creating post</h4>
    <mp-input v-focus v-model="post.title" type="text" placeholder="Title" />
    <mp-input v-model="post.body" type="text" placeholder="Description" />
    <mp-button
      style="align-self: flex-end; margin-top: 15px"
      @click="createPost"
    >
      Create
    </mp-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },

  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style>
form {
  display: flex;
  flex-direction: column;
}
</style>
