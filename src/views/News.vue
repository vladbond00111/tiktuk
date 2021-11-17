<template>
  <div class="news-wrap">
<!--    <img alt="Vue logo" src="../assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
<!--    <v-btn @click="getData">adff</v-btn>-->
    <v-row>

      <v-col
          v-for="(item, i) in trendingFeed"
          :key="i"
          cols="12"
          lg="3"
      >
        <NewsCard :item="item"></NewsCard>
      </v-col>
    </v-row>
  </div>
</template>

<script>
// @ is an alias to /src
import store from '../store'
import NewsCard from '@/components/NewsCard.vue'
// import axios from "axios";

export default {
  name: 'News',
  components: {
    NewsCard
  },
  data () {
    return {
      test: null
    }
  },
  computed: {
    trendingFeed() {
      return store.state.news.trendingFeed
    }
  },
  mounted() {
    store.dispatch('news/getTrendingFeed')
  },
  methods: {
    getData () {
    }
  }
}
</script>

<style lang="scss">
.news-wrap {
  padding: 10px 30px;
}
</style>
