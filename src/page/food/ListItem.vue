<template>
  <li class="wx-listItem"
      @click="$router.push({name: 'shopDetail', params: {shopId: shopInfo.id}})">
    <div class="wx-listItem__imgWrap">
      <img v-lazy="shopInfo.logoPath"
           class="page-lazyload-image" />
    </div>
    <div class="wx-listItem__rightContent">
      <div class="wx-listItem__shopName">{{ shopInfo.shopName }}</div>
      <div class="wx-listItem__shopWrap">
        <div class="wx-listItem__shopType background-theme">{{ shopInfo.c_title }}</div>
        <div class="wx-listItem__shopFloor">{{ shopInfo.floorName }} {{ shopInfo.address ? '-' : '' }} {{ shopInfo.address }}</div>
      </div>
      <div class="wx-listItem__shopSlogan">
        <span v-if="shopInfo.shortText">活动 · </span>
        <span>{{ shopInfo.shortText }} &nbsp;</span>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  name: 'ListItem',

  props: {
    shopInfo: {
      type: Object,
    }
  }
};
</script>

<style lang="scss" scoped>
@include b(listItem) {
  width: rem(344);
  background-color: #fff;
  box-shadow: 0 rem(5) rem(30) rem(-20) #000;
  &:nth-child(n + 3) {
    margin-top: rem(30);
  }

  @include e(imgWrap) {
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: rem(306);
    img {
      width: 100%;
    }
  }

  @include e(rightContent) {
    padding: rem(20);
    display: flex;
    flex-flow: row wrap;
    align-content: space-between;
  }

  @include e(shopName) {
    width: 100%;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    font-size: rem(32);
    font-weight: bold;
    color: #000000;
  }

  @include e(shopWrap) {
    margin-top: rem(16);
    width: 100%;
    display: flex;
    justify-content: space-between;
  }

  @include e(shopType) {
    padding: 0 rem(8);
    height: rem(32);
    // line-height: rem(30);
    font-size: rem(24);
    color: #fff;
    border-radius: rem(4);
  }

  @include e(shopFloor) {
    font-size: rem(24);
    color: #a8a8a8;
  }

  @include e(shopSlogan) {
    margin-top: rem(16);
    display: block;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    color: #ff5152;
  }
}
</style>
