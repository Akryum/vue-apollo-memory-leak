<template>
  <div class="test-many">
    <h1>Many nodes</h1>
    <Post v-for="post in list" :key="post.uuid" :post="post"/>
  </div>
</template>

<script>
import Post from "./Post";


export default {
  name: "TestMany",

  components: { Post },

  data() {
    return {
      list: this.getNodes(),
      countries: null
    };
  },

  methods: {
    getNodes() {
      const count = 1000;
      let list = [];
      for (let i = 0; i < count; i++) {
        const uuid = Math.random();
        list.push({
          uuid,
          comment: `${uuid} - lorem`
        });
      }

      return list;
    },
  }
};
</script>
