<template>
  <div class="tab-bar-item" @click="itemClick" :style="activeBorderStyle">
    <!-- slot 盡量不要綁東西 有些會出錯 -->
    <div class="itemIcon" v-if="!isActive">
      <slot name="item-icon"></slot>
    </div>
    <div class="itemIcon" v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div class="itemText" :style="activeFontStyle">
      <!-- slot 不能綁定 class 會被替換掉 -->
      <slot name="item-text"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabBarItem",
  props: {
    path: {
      type: String,
      require: true,
    },
    activeColor:{
      type: String,
      default: 'red'
    }
  },
  data() {
    return {
      // isActive: false,
    };
  },
  computed: {
    isActive() {
      // this.$route = 哪個活躍 就抓哪個
      // return this.path == this.$route.path ? true : false;
      return this.$route.path.indexOf(this.path) !== -1
    },
    activeFontStyle() {
      return this.isActive ? { color: this.activeColor} : {}
    },
    activeBorderStyle(){
      return this.isActive ? { borderTop: "1px solid " + this.activeColor} : {}
    }
  },
  methods: {
    itemClick() {
      this.$router.replace(this.path);
    },
  },
};
</script>

<style lang="scss" scoped>
.tab-bar-item {
  flex: 1;
  text-align: center;
  height: 49px; // tabbar 常用高度
  font-size: 14px;
  border: 1px solid transparent;
  transition: border 0.2s ease-out;
}

.tab-bar-item img {
  width: 24px;
  height: 24px;
  margin-top: 3px;
  margin-bottom: 3px;
  vertical-align: middle;
}
.tab-bar-item .itemIcon{
  transition: 5s ease-out;
}
.tab-bar-item .itemText{
  transition: color 0.2s ease-out;
}


</style>