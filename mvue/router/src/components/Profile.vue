<template>
  <div class="Profile">
    <h1>This is Profile of {{UserId}}</h1>

  </div>
</template>

<script>
export default {
  name: 'Profile',
  data () {
    return {
      UserId:this.$route.params.user_id
    }
  },
  methods:{
    updateId(){
      this.UserId = this.$route.params.user_id
    }
  },
  watch:{
    $route:'updateId'
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: bold;
  color: red;
}
</style>
