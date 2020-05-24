<template>
<div class = "container d-flex justify-content-center">
  <div class="card w-25" v-for="post in posts" v-bind:key = "post._id">
    <div class = "card-body">
      <p class = "card-text">ID: {{post.id}}</p>
    <p class = "card-text">Username: {{post.username}}</p>
    </div>
  </div>
</div>
</template>

<script>
import axios from "axios";

const url = "http://localhost:3000/users"



export default {
  name: 'HelloWorld',
  data(){
    return {
      posts:[]
    }
  },
  async created()
  {
    this.posts = await axios.get(url).then(function (response) {
    // handle success
    return response.data
  })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
