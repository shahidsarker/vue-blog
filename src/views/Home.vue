<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  name: "Home",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        title: "Welcome to the blog",
        body: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quam velit voluptatibus sed officiis dolor, harum culpa dolores incidunt autem exercitationem fuga tempore, odit quibusdam amet repellendus cumque? Iusto, maiores cumque.",
        id: 1,
      },
      {
        title: "Top 5 CSS Tips",
        body: "Animi delectus ipsa, eius voluptatibus pariatur cupiditate amet soluta maxime doloribus, ab placeat, voluptas esse aut molestias beatae dicta debitis repellat at eligendi nemo velit. Excepturi quo unde veritatis alias!",
        id: 2,
      },
    ]);
    const showPosts = ref(true);

    return { posts, showPosts };
  },
};
</script>
