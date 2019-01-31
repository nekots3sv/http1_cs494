<template>
  <div class="about">
    <h2>{{ httpdata }}</h2>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      httpdata: ""
    };
  },
  mounted() {
    axios({
      method: "GET",
      url: "http://jsonplaceholder.typicode.com/todos"
    }).then(result => {
      this.httpdata = result.data;
    });
  }
};
</script>