<template>

    <div class="main_back">
        <div class="header"></div>
        <h1>O.dev test task</h1>
        <ul v-for="(value, key) in posts" v-bind:key="value">
            <template v-if="key === 'rates'">
                    <table>
                        <tr>
                            <th class="f_th">Currency</th>
                            <th>Rate</th>
                        </tr>
                    </table>
                <p v-for="(values, key) in value" v-bind:key="values">
                    <table>
                        <tr>
                            <th class="f_th">
                            <span class="left">{{key}}</span>
                            </th>
                            <th>
                            <span class="left">{{values}}</span>
                            </th>
                        </tr>
                    </table>
                </p>
            </template>
            <template v-else>
                <table>
                    <tr>
                        <th class="f_th">
                            <span class="left">{{key}}</span>
                        </th>
                        <th class="f_th">
                            <span class="left">{{value}}</span>
                        </th>
                    </tr>
                </table>
            </template>
        </ul>
    </div>
</template>

<script>
  import axios from 'axios';
export default {
  name: 'App',
  data() {
    return {
      posts: [],
      errors: []
    }
  },

  // Fetches posts when the component is created.
  created() {
    axios.get(`https://api.exchangeratesapi.io/latest`)
    // axios.get(`http://jsonplaceholder.typicode.com/posts`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.posts = response.data
        // console.log(response)
    })
    .catch(e => {
      this.errors.push(e)
    })

    // async / await version (created() becomes async created())
    //
    // try {
    //   const response = await axios.get(`http://jsonplaceholder.typicode.com/posts`)
    //   this.posts = response.data
    // } catch (e) {
    //   this.errors.push(e)
    // }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
  table{
    width: 400px;
    margin-left: auto;
      margin-right: auto;
  }
  table, th, td{
    border: 1px solid #000;
    border-collapse: collapse;

  }
  tr:nth-child(even){
    background-color: #fff;
      text-align: left;

  }
  tr:nth-child(odd){
    background-color: #ddd;
      text-align: left;
  }
.main_back {
    background-image: url("assets/back1.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    border: 4px;
    margin-top: 1px;
}
h1{
    font-family: "Poppins";
    text-align: center;
    font-weight: 100;
    color: #000000;
    margin-top: 1px;
}
    .f_th{
        width: 50%;
    }

</style>
