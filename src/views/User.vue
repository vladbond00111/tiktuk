<template>
  <div class="user">
    <UserInfo :userInfo="userInfo"></UserInfo>
<!--    <v-row>-->
<!--      <v-col-->
<!--          v-for="(item, i) in userFeed"-->
<!--          :key="i"-->
<!--          cols="12"-->
<!--          lg="3"-->
<!--      >-->
<!--        <NewsCard :item="item"></NewsCard>-->
<!--      </v-col>-->
<!--    </v-row>-->
  </div>
</template>

<script>
// @ is an alias to /src
import store from '../store'
import UserInfo from '@/components/UserInfo.vue'
// import NewsCard from '@/components/NewsCard.vue'
// import axios from "axios";

export default {
  name: 'News',
  components: {
    UserInfo
    // NewsCard
  },
  data () {
    return {
      test: null
    }
  },
  computed: {
    userInfo() {
      return store.state.news.userInfo
    },
    userFeed() {
      return store.state.news.userFeed
    }
  },
  mounted() {
    store.dispatch('news/getUserInfo', this.$route.params.id)
    // store.dispatch('news/getUserFeed', this.$route.params.id)
  },
  methods: {
    getData () {
    }
  }
}
</script>