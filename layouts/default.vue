<template>
  <el-container>
    <el-header>
      <el-menu mode="horizontal">
        <el-menu-item>
          <nuxt-link to="/" />
        </el-menu-item>
        <template v-if="userInfo.id">
          <el-menu-item>
            <a>退出</a>
          </el-menu-item>
          <el-menu-item>
            <span>{{ userInfo.nickname }}</span>
          </el-menu-item>
          <el-menu-item>
            <nuxt-link to="/editor/new">
              写文章
            </nuxt-link>
          </el-menu-item>
        </template>
        <template v-else>
          <el-menu-item>
            <nuxt-link to="/register">
              注册
            </nuxt-link>
          </el-menu-item>
          <el-menu-item>
            <nuxt-link to="/login">
              登录
            </nuxt-link>
          </el-menu-item>
        </template>
      </el-menu>
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer />
  </el-container>
</template>
<script>
export default {
  computed: {
    userInfo() {
      return this.$store.state.user
    }
  },
  mounted() {
    this.getUserInfo()
  },
  methods: {
    getUserInfo() {
      const token = localStorage.getItem('token')
      if (token) {
        this.$store.dispatch('user/detail')
      }
    }
  }
}
</script>
<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
