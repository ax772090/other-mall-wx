<template>
  <div class="wx-detailIntro">
    <h3 class="wx-detailIntro__title">{{ activityData.info.title }}</h3>
    <div class="wx-detailIntro__row address">
      <span class="wx-detailIntro__leftTitle">地点</span>
      <p class="wx-detailIntro__rightContent">{{ activityData.info.address }}</p>
    </div>
    <!-- <div class="wx-detailIntro__row brief-info">
      <span>简介</span>
      <p class="wx-detailIntro__rightContent">
        {{ activityData.info.remark }}
      </p>
    </div> -->
  </div>
</template>

<script>
export default {
  props: {
    activityData: {
      type: Object,
    },
  },
};
</script>

<style lang="scss" scoped>
@include b(detailIntro) {
  // border-top: rem(30) solid #f0f2f5;
  padding: rem(12) rem(24) rem(20);
  background-color: #fff;

  @include e(title) {
    line-height: rem(70);
    font-size: rem(32);
    font-weight: bold;
  }

  @include e(row) {
    margin-top: rem(14);
    display: flex;
    flex-flow: row nowrap;
    // justify-content: space-between;
    font-size: rem(26);
  }

  @include e(leftTitle) {
    font-size: rem(26);
    font-weight: bold;
  }

  // @include e(leftContent) {
  //   font-weight: bold;
  //   display: inline-block;
  //   width: rem(78);
  //   // TODO: 不加flex-shrink会导致有的被压缩宽度的现象
  //   flex-shrink: 0;
  // }

  @include e(rightContent) {
    margin-left: rem(20);
    display: inline-block;
    color: #959595;
  }
}
</style>


