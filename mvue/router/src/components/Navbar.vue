<template>
  <div>
    <nav>
      <ul>
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <li>
          <router-link to="/About">About</router-link>
        </li>
        <li>
          <router-link to="/Contact">Contact</router-link>
        </li>
        <!-- <li>
          <router-link to="/Profile"></router-link>
        </li> -->
      </ul>
    </nav>
    <div>
      <ul>
        <li v-for="(id, index) in userIds" :key="index">
          <router-link :to ="{name:'Profile', params:{user_id:id}}">Profile{{id}}</router-link>
        </li>
      </ul>
      <button @click="About">About</button>
      <button @click="Contact">Contact</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      userIds: ['1', '2', '3', '4', '5']
    }
  },
  methods:{
    Contact(){
      this.$router.push({name:'Contact'})
    },
    About(){
      this.$router.push({name: 'About'})
    }
  }
}
</script>

<style scoped>
nav {
  text-align: center;
  width: 100%;
  height: fit-content;
  background-color: lightgreen;
}

nav ul {
  margin: 0%;
  padding: 0;
}

nav li {
  display: inline-block;
  list-style: none;
  margin: 0%;
  padding: 10px 15px;
}
a.router-link-exact-active{
  color:black;
}
</style>
