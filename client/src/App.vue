<template>
  <div id="app">
<!--    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">-->
    <router-view/>
  </div>
</template>

<script>
  import { useRouter } from "vue-router";
  import {getUserInfo} from './mgr/userMgr'

  export default {
    name: 'App',
    data() {
      return {
      }
    },
    created() {
      this.router = useRouter()
      this.$nextTick(() => {
        let user = getUserInfo()
        if (user) {
        } else {
          if (window.location.pathname === '/login' || window.location.pathname === '/') {
            this.router.push('/login')
          }
        }
      })
    },
    components: {
    },
    methods: {
    }
  }
</script>
<!-- 引入组件库 -->
<style lang="scss">
  //@import "common/scss/reset";
  //@import "common/scss/element";
  //@import 'common/scss/icon.css';

  @use "common/scss/reset" as *;
  @use "common/scss/element" as *;
  @use "common/scss/icon.css" as *;

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
  body {
    background-color: white;
  }
</style>
