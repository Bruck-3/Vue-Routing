<template>
  <div id="app">
    <div id="nav">
      <router-link :to="{ name: 'Home' }">Home</router-link>|
      <router-link :to="{ name: 'About' }">About</router-link>|
      <router-link :to="{ name: 'Contact' }">Contact</router-link>|
      <router-link :to="{ name: 'Calculate' }">Calculate</router-link>
    </div>
    <h3>Users</h3>
    <ul id="profile">
      <li v-for="(id, index) in user_id" :key="index">
        <router-link :to="{ name: 'Profile', params: { user_id: id } }"
          >profile of {{ id }}</router-link
        >
      </li>
    </ul>
    <ul id="buttons">
      <li>
        <button @click="goBack">Go Back</button>
      </li>
      <li>
        <button @click="goHome">Go Home</button>
      </li>
      <li>
        <button @click="goForward">Go Forward</button>
      </li>
    </ul>
    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      user_id: ["1", "2", "3"]
    };
  },
  methods: {
    goHome() {
      this.$router.push({ name: "Home" });
    },
    goBack() {
      this.$router.go(-1);
    },
    goForward() {
      this.$router.go(1);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
#profile {
  list-style-type: none;
}
#profile li {
  display: inline-block;
  margin: 10px;
}
#buttons {
  list-style-type: none;
}
#buttons li {
  display: inline-block;
  margin: 10px;
}
</style>
