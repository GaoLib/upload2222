<template>
  <div class="container">
    <div>
      <VirtualList :listData="articles" />
    </div>
  </div>
</template>

<script>
import VirtualList from '~/components/VirtualList.vue'

export default {
  components: {
    VirtualList
  },
  data() {
    return {
      articles: [
        {
          views: 3,
          like: 0,
          _id: 1,
          title: 'teessstt'
        },
        {
          views: 3,
          like: 0,
          _id: 2,
          title: '2222222'
        }
      ]
    }
  }
  // async mounted() {
  //   const ret = await this.$http.get('/article')
  //   if (ret.code === 0) {
  //     this.articles = ret.data
  //   }
  // }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
