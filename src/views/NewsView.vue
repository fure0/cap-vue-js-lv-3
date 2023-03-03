<template>
  <div>
    <p v-for="item in this.$store.state.news" v-bind:key="item.id">
      <a v-bind:href="item.url">{{ item.title }}</a>
      <small>{{item.time_ago}}, {{ item.user }}</small>
    </p>
  </div>
</template>

<script>

export default {
  created() {
    this.$store.dispatch('FETCH_NEWS')

    // fetchNewsList()
    //   .then(response => {
    //     console.log(response);
    //     this.users = response.data;
    //   })
    //   .catch(function(error) {
    //     console.log(error)
    //   })
  },
}
</script>

<style>

</style>