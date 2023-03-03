<template>
  <div>
    <p v-for="item in fetchedAsk" v-bind:key="item.id">
      <a v-bind:href="item.url">{{ item.title }}</a>
      <small>{{item.time_ago}}, {{ item.user }}</small>
    </p>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';
// import { mapState } from 'vuex';

export default {
  computed: {
    // #4
    ...mapGetters([
      'fetchedAsk'
    ])

    // #3
    // ...mapGetters({
    //   fetchedAsk: 'fetchedAsk'
    // })
    
    // #2
    // ...mapState({
    //   fetchedAsk: state => state.ask
    // })

    // #1
    // fetchedAsk() {
    //   return this.$store.state.ask;
    // }
  },
  created() {
    this.$store.dispatch('FETCH_ASK');
  }
}
</script>

<style>

</style>