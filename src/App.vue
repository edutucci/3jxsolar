<template lang="pug">
<router-view/>
</template>

<script>

export default {
  data() {
    return {
      showDrawer: false,
    };
  },
  methods: {
    onBtnClick() {
      this.showDrawer = !this.showDrawer;
    },
  },
};
</script>

// <style lang="stylus">
// #app
//   font-family Avenir, Helvetica, Arial, sans-serif
//   -webkit-font-smoothing antialiased
//   -moz-osx-font-smoothing grayscale
//   text-align center
//   color #2c3e50
//   margin-top 60px
// </style>

<style scoped>
.menubar {
  background: darkorange;
}

.menuitem {
  width: auto;
  color: white;
  padding: 5px;
  font-weight: bold;
}
</style>
