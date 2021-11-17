<template>
  <v-card
      v-if="userInfo && userInfo.user"
      class="mx-auto"
      outlined
  >
    <v-list-item three-line>
      <v-list-item-avatar
          tile
          size="120"
          color="grey"
      >
        <v-img
            class="elevation-6"
            alt=""
            :src="userInfo.user.avatarMedium"
        ></v-img>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="text-overline mb-4">
          {{ userInfo.user.nickname }}
        </div>
        <v-list-item-title class="text-h5 mb-1">
          <a href="userInfo.user.bioLink.link" v-if="userInfo.user.bioLink">
            {{ userInfo.user.bioLink.link }}
          </a>
        </v-list-item-title>
        <v-list-item-subtitle>{{ userInfo.user.signature }}</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
  </v-card>
</template>

<script>
  export default {
    name: 'UserInfo',
    props: {
      userInfo: {
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
</style>