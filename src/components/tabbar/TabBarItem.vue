<template>
  <div class="tab-bar-item" @click="itemClick">
    <slot v-if="!isActive" name="item-icon"></slot>
    <slot v-else name="item-active-icon"></slot>
    <div :class="{ active: isActive }"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
export default {
  props: {
    path: String,
    activeColor: {
      type: String,
      default: "red",
    },
  },
  data() {
    return {
      //isActive: true,
    };
  },
  computed:{
      isActive(){
        return this.$route.path.indexOf(this.path)!==-1;
      }
  },
  methods: {
    itemClick() {
      if (this.$route.path == this.path) {
        return;
      }
      this.$router.replace(this.path);
    },
  },
};
</script>

<style>
.tab-bar-item {
  font-size: 14px;
  flex: 1;
  text-align: center;
  height: 49px;
}
.tab-bar-item img {
  margin-bottom: 2px;
  vertical-align: middle;
  margin-top: 3px;
  width: 24px;
  height: 24px;
}
.active {
  color: red;
}
</style>