<template>
  <div>
    <!-- 二级路由 -->
    <router-view></router-view>
    <!-- 导航栏 -->
    <!-- 路由模式：拿item的to属性和当前路由的path对比，如果一样的话高亮 -->
    <van-tabbar route>
      <van-tabbar-item to="/ ">
        <template #icon>
          <span class="toutiao toutiao-shouye"></span>
          <span class="text">首页</span>
        </template>
      </van-tabbar-item>
      <van-tabbar-item to="/videos">
        <template #icon>
          <span class="toutiao toutiao-shipin"></span>
          <span class="text">视频</span>
        </template>
      </van-tabbar-item>
      <van-tabbar-item to="/qa">
        <template #icon>
          <span class="toutiao toutiao-wenda"></span>
          <span class="text">问答</span>
        </template>
      </van-tabbar-item>
      <van-tabbar-item to="/profile">
        <template #icon>
          <span class="toutiao toutiao-wode"></span>
          <span class="text">{{ isLogin ? '我的' : '未登录' }}</span>
        </template>
      </van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  data() {
    return {
      active: 0
    }
  },
  computed: {
    ...mapGetters(['isLogin'])
  }
}
</script>

<style scoped lang="less">
:deep(.van-tabbar-item__icon) {
  display: flex;
  height: 100%;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  font-size: 30px;
}
.toutiao {
  font-size: 40px;
}
</style>
