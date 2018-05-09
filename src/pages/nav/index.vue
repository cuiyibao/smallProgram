<template>
  <div>
    <div class="page">
      <div class="weui-tab">
        <div class="weui-tab__content">
          <div class="kind-list__item">
            <a href="/pages/index/index">首页</a>
          </div>
          <div class="kind-list__item">
            <a href="/pages/register/register">注册</a>
          </div>
          <div class="kind-list__item">
            <a href="/pages/launch/launch">活动发起</a>
          </div>
          <div class="kind-list__item">
            <a href="/pages/detail/detail">活动详情</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      name: "nav"
    }
  },

  created () {
  }
}
</script>

<style lang="scss" scoped>
 page,
.page,
.page__bd {
    height: 100%;
}
.page__bd {
    padding-bottom: 0;
}
.weui-tab__content {
    padding-top: 60px;
    text-align: center;
    a {
      color: #2b17df;
    }
}
.kind-list__item {
    margin: 10px 0;
    background-color: #fff;
    border-radius: 2px;
    overflow: hidden;
    font-size: 18px;
}
</style>
