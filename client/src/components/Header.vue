<template>
  <div>
    <div class="nv-navbar">
      <ul class="nav">
        <li><router-link :to="{ name: 'blogs' }"> Blogs </router-link></li>
        <li><router-link :to="{ name: 'users' }"> Users </router-link></li>
        <li><router-link :to="{ name: 'comments' }"> Comments</router-link></li>
        <li><router-link :to="{ name: 'login' }"> Login </router-link></li>
        <li><a v-on:click.prevent="logout" herf="#">Logout</a></li>
      </ul>
      <div class="clearfix"></div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    logout() {
      this.$store.dispatch("setTkoen", null);
      this.$store.dispatch("setComment", null);
      this.$router.push({
        name: "login",
      });
    },
  },
};
</script>
<style scoped>
.nv-navbar {
  background-color: palegoldenrod;
  width: 100%;
  padding: 0px 0px 0px 0px;
}
.nv-navbar .nav {
  list-style: none;
  margin: 0;
  padding: 0;
  float: left;
}
.nv-navbar .nav li {
  float: left;
}
.nv-navbar .nav li a {
  padding: 10px;
  text-decoration: none;
  color: gray;
  font-weight: bold;
}
.nv-navbar .nav li a:hover {
  padding: 10px;
  text-decoration: none;
  color: darkslategrey;
}
.nv-navbar .nav li a.router-link-active {
  background-color: gold;
  color: darkolivegreen;
}
.clearfix {
  clear: left;
}
</style>
