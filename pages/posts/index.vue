<template>
  <div>
    <div>
      <h2>API request test</h2>
      <p style="display: inline">object returned from</p>
      <a href="https://jsonplaceholder.typicode.com/todos"
        >jsonplaceholder.typicode.com/todos</a
      >
    </div>
    <hr />

    <div class="container-fluid">
      <!-- {{ posts }} -->

      <!-- vue v-bind:key is used to render list object -->
      <!-- <h4 v-for="post in posts" :key="post.id">{{ post.title }}</h4> -->
    </div>
    
    <div class="container row">
      <!-- render in Card component -->
      <Card v-for="post in posts" :key="post.id" :post="post" />
    </div>
  </div>
</template>

<script>
// async await API request(simpler)
import axios from "axios";
import Card from "@/components/Card";

export default {
  components: {
    Card,
  },

  data() {
    return { posts: "null" };
  },

  //async awaits for the operation to complete before fetching
  async asyncData() {
    //destructuring data response(straightforward)
    let { data } = await axios.get(
      "https://jsonplaceholder.typicode.com/todos"
    );
    return { posts: data };
  },
};
</script>

<!--
<script>
// async await API request(simpler)
import axios from "axios";

export default {
  data() {
    return { posts: "null" };
  },

  //async awaits for the operation to complete before fetching
  async asyncData() {
    //destructuring data response(straightforward)
    let {data} = await axios.get("https://jsonplaceholder.typicode.com/todos");
    return { posts: data };
  },
};
</script>
-->

<!--
<script>
// async await API request(simpler)
import axios from "axios";

export default {
  data() {
    return { posts: "null" };
  },

  //async awaits for the operation to complete before fetching
  async asyncData() {
    let response = await axios.get("https://jsonplaceholder.typicode.com/todos");
    return { posts: response.data };
  },
};
</script>
-->

<!--<script>
//async request API
import axios from "axios";

export default {
  data() {
    return { posts: "null" };
  },

  asyncData() {
    return axios
      .get("https://jsonplaceholder.typicode.com/todos")
      .then((res) => {
        console.log(res);
        return { posts: res.data };
      });
  },
};
</script>
-->

<!--<script>
// dont forget to restart server when switching to async
export default {
  asyncData(context){
    // console log is displaying server-side context object
    console.log(context);
  }
};
</script>-->

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