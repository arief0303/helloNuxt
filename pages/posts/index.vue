<template>
  <div>
    <div>
      <h2>API request test</h2>
    </div>
    <hr />
    <div class="container-fluid">
      <h4 v-for="post in posts" :key="post.id">{{ post.title }}</h4>
    </div>
  </div>
</template>

<script>
// dont forget to restart server when switching to async
export default {
  asyncData(context){
    // console log is displaying server-side context object 
    console.log(context);
  }
};
</script>

<!-- 
<script>
// API request via axios(client side only)
import axios from "axios";

export default {
  data() {
    return {
      posts: [],
    };
  },

  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos")

      .then((response) => {
        console.log(response);
        this.posts = response.data;
      })

      .catch((error) => {
        console.log(error);
      });
  },
};
</script>
-->