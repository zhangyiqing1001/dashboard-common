<template>
  <div class="page-card-detail d-flex border p-4 align-items-center">
    <div class="img mr-5">
      <img style="width: 80px;" ref="imgRef" @error="getDefaultImg" :src="img" :alt="pageTitle" />
    </div>
    <div class="text-wrap">
      <div class="title">{{ pageTitle }}</div>
      <slot />
      <div class="description mt-2">{{ description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PageCardDetail',
  props: {
    img: {
      type: String,
    },
    pageTitle: {
      type: String,
      required: true,
    },
    description: {
      type: String,
    },
  },
  data () {
    return {
      defaultImg: require('../../assets/images/invalidImg.svg'),
    }
  },
  methods: {
    getDefaultImg () {
      this.$refs.imgRef.src = this.defaultImg
    },
  },
}
</script>

<style lang="less" scoped>
.page-card-detail {
  .text-wrap {
    .title {
      color: #000;
      font-size: 20px;
    }
    .description {
      color: #ccc;
    }
  }
}
</style>
