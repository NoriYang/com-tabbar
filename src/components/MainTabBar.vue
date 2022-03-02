<template>
    <tab-bar>
      <tab-bar-item path="/home">
        <img slot="item-icon" src="~@/assets/img/tabbar/home.svg" alt="">
        <img slot="item-icon-active" src="~@/assets/img/tabbar/home_active.svg" alt="">
        <div slot="item-text">首頁</div>
      </tab-bar-item>
      <tab-bar-item path="/category">
        <img slot="item-icon" src="~@/assets/img/tabbar/category.svg" alt="">
        <img slot="item-icon-active" src="~@/assets/img/tabbar/category_active.svg" alt="">
        <div slot="item-text">分類</div>
      </tab-bar-item>
      <tab-bar-item path="/cart">
        <img slot="item-icon" src="~@/assets/img/tabbar/cart.svg" alt="">
        <img slot="item-icon-active" src="~@/assets/img/tabbar/cart_active.svg" alt="">
        <div slot="item-text">購物車</div>
      </tab-bar-item>
      <tab-bar-item path="/profile">
        <img slot="item-icon" src="~@/assets/img/tabbar/profile.svg" alt="">
        <img slot="item-icon-active" src="~@/assets/img/tabbar/profile_active.svg" alt="">
        <div slot="item-text">個人檔案</div>
      </tab-bar-item>
    </tab-bar>
</template>

<script>
import TabBar from '@/components/tabbar/TabBar.vue'
import TabBarItem from '@/components/tabbar/TabBarItem.vue'
export default {
  name: "MainTabBar",
  components:{
    TabBar,
    TabBarItem
  }
}
</script>

<style>

</style>