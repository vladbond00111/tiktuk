<template>
  <v-card
      class="mx-auto"
      color="#010101"
      dark
  >
    <v-card-title>
    </v-card-title>

    <v-card-text class="text-h5 font-weight-bold">
      <div>
        <video class="mx-auto col video" controls autoplay muted>
<!--          <sourse :src="item.videoUrl" />-->
          <source :src="item.videoUrl">
<!--          <source src="https://v16m.tiktokcdn.com/ea7621f71984acec1df3bfcceeae21fc/61954c17/video/tos/useast2a/tos-useast2a-pve-0068/ec6e0ec0174f450f9a25b16568219e4f/?a=1233&br=2834&bt=1417&cd=0%7C0%7C1&ch=0&cr=0&cs=0&cv=1&dr=0&ds=3&er=&ft=wZ~R_F5qkag3-I&l=20211117123801010191057015120AB82A&lr=tiktok_m&mime_type=video_mp4&net=0&pl=0&qs=0&rc=M2VvZmU6ZjltODMzNzczM0ApOGloOWk3Zzs8N2lpNWc4O2dwLXJxcjRfbGFgLS1kMTZzc2MyYWMwYDUuYWMxMDYuYDQ6Yw%3D%3D&vl=&vr=">-->
        </video>
      </div>
      <div>
        {{ item.text }}
      </div>
    </v-card-text>
    <div class="name-wrap">
      <div>
        <router-link :to="'/user/'+ item.authorMeta.name" class="user-link">
          <v-list-item-avatar color="grey darken-3">
            <v-img
                class="elevation-6"
                alt=""
                :src="item.authorMeta.avatar"
            ></v-img>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title class="avatar-img">
              {{ item.authorMeta.nickName }}
            </v-list-item-title>
          </v-list-item-content>
        </router-link>
      </div>
      <div>
        <div class="stat-item">
          <v-icon class="mr-1">
            mdi-heart
          </v-icon>
          <span class="subheading mr-2">{{ item.diggCount }}</span>
        </div>
        <div class="stat-item">
          <v-icon class="mr-1">
            mdi-comment
          </v-icon>
          <span class="subheading">{{ item.commentCount }}</span>
        </div>
      </div>
    </div>
  </v-card>
</template>

<script>
  export default {
    name: 'NewsCard',
    props: {
      item: {
        type: Object,
        default: () => {}
      }
    },
    data: () => ({
    }),
    mounted() {}
  }
</script>

<style lang="scss">
.name-wrap {
  padding: 10px 30px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  .user-link {
    text-decoration: none;
    .avatar-img {
      color: white;
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
    }
  }
  .stat-item:first-child {
    margin-bottom: 10px;
  }
}
</style>