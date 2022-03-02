<template>
    <div id="tab-bar">
      <slot></slot>
    </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#tab-bar {
  display: flex;
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #f6f6f6;
  margin: 0;
  padding: 0;
}
</style>